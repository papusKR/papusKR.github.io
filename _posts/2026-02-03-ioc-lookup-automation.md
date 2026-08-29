---
title: "IOC 조회 자동화 스크립트 (블로그 테스트용 글)"
date: 2026-02-03
categories: [Operations, Automation]
tags: [python, ioc, api, automation]
description: "의심 IP 하나 확인하는 데 매번 사이트 여러 곳을 여는 게 비효율적이라 만든 것."
---

더미 글입니다.

## 문제

의심 IP가 나오면 매번 여러 사이트를 각각 열어 확인했습니다.
건당 3분, 하루 40건이면 두 시간입니다.

## 만든 것

```python
import asyncio, httpx

async def lookup(client, name, url):
    try:
        r = await client.get(url, timeout=10)
        return name, r.json()
    except Exception as e:
        return name, {"error": str(e)}

async def enrich(ip: str):
    async with httpx.AsyncClient() as client:
        tasks = [
            lookup(client, "geo", f"https://example-geo.invalid/{ip}"),
            lookup(client, "rep", f"https://example-rep.invalid/{ip}"),
        ]
        return dict(await asyncio.gather(*tasks))

if __name__ == "__main__":
    print(asyncio.run(enrich("203.0.113.10")))
```

## 결과

건당 3분에서 10초로 줄었습니다.
