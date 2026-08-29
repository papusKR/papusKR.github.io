---
title: "윈도우 이벤트 로그로 타임라인 재구성하기 (블로그 테스트용 글)"
date: 2026-02-11
categories: [보안]
tags: [windows, eventlog, timeline, dfir]
description: "계정 탈취 의심 건에서 로그온 이벤트만으로 침입 시점을 좁힌 과정."
pinned: true
---

더미 글입니다.

## 수집

```bash
wevtutil epl Security C:\evidence\security.evtx
wevtutil epl Microsoft-Windows-Sysmon/Operational C:\evidence\sysmon.evtx
```

## 파싱

```python
import pandas as pd
from evtx import PyEvtxParser

parser = PyEvtxParser("security.evtx")
df = pd.DataFrame([r for r in parser.records_json()])

logons = df[df["event_id"].isin([4624, 4625, 4672])]
logons.sort_values("timestamp").head(20)
```

## 본 것

- 4625가 짧은 간격으로 반복된 뒤 4624 성공
- 직후 4672로 특수 권한 부여
- 원격 로그온 유형이 평소와 다름

## 정리

로그온 이벤트만으로도 진입 시점은 상당히 좁혀집니다.
그 다음에 프로세스 생성 로그를 붙이면 무엇을 했는지가 보입니다.
