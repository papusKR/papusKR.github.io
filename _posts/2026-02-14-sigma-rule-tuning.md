---
title: "Sigma 룰 오탐 튜닝 기록"
date: 2026-02-14
categories: [Detection, Sigma]
tags: [sigma, siem, tuning, attack]
description: "PowerShell 인코딩 명령 탐지 룰이 하루 200건씩 울려서, 정탐만 남기기까지 한 일."
---

더미 글입니다. 레이아웃과 코드블록 확인용으로 남겨둔 샘플이니, 실제 글을 쓰면 지우세요.

## 상황

특정 탐지 룰이 하루 200건 넘게 울리는데 정탐은 한 자릿수였습니다.
알람 피로도가 올라가면 정작 봐야 할 것을 놓칩니다.

## 원본 룰

```yaml
title: Suspicious PowerShell Encoded Command
id: 8a1b2c3d-0000-0000-0000-000000000001
status: experimental
logsource:
  product: windows
  category: process_creation
detection:
  selection:
    Image|endswith: '\powershell.exe'
    CommandLine|contains: '-enc'
  condition: selection
level: medium
```

## 무엇이 문제였나

| 발생원 | 비중 | 성격 |
|---|---|---|
| 자산관리 에이전트 | 62% | 정상 |
| 백업 스케줄러 | 21% | 정상 |
| 사용자 단말 | 17% | 확인 필요 |

## 튜닝 후

```yaml
detection:
  selection:
    Image|endswith: '\powershell.exe'
    CommandLine|contains:
      - '-enc'
      - '-EncodedCommand'
  filter_agent:
    ParentImage|endswith:
      - '\assetagent.exe'
      - '\backupsvc.exe'
  condition: selection and not filter_agent
level: high
```

## 결과

하루 200건대에서 12건대로 줄었고, 정탐 누락은 없었습니다.
제외 조건은 부모 프로세스 경로로만 걸었습니다. 명령줄 문자열로 거르면
공격자가 흉내내는 순간 그대로 뚫립니다.
