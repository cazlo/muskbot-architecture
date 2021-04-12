## Status
accepted

## Context
trade sim jobs can take quite a bit of time to run.
the trade sim job algorithm is very synchronous in nature:
```
tradeHistory = []
for each ticker in allTickersForJobTimeframe(begin, end):
   given current trade history
   and current tick
   does strategy handler indicate we buy, sell, or hold?
```

## Decision
1. have create job handler (`POST /cryptoSimJob`) save job, then kick off promise to do job, but not await on that promise
2. spin up a small recurring task to mark jobs as 'done' if they are older than 5 minutes

## Consequences

### good
- job creation is fast
- solution delivered fast

### bad
- OOME can sometimes happen for really big job timeframes
- no guarantee jobs will actually finish -> some component must "timeout" jobs after some expected interval
- sometimes jobs running on same box as API causes 'noisy neighbor' problem where API calls take a long time because they are blocked by job computation