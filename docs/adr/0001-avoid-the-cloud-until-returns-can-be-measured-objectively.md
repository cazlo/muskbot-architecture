## Status
accepted

## Context
Cloud computation costs more than locally available computation

I got a nice computer here to run the cluster from

    CPU - AMD Ryzen 7 3700X 8-Core (16 computation threads)

    Memory - 32 GB

    GPU - AMD 5700xt 8GB (1605-1755 MHz core, 1750 MHz memory)

    SSD - 1TB 970 EVO Plus SSD (3,500MB/s read and 3,300MB/s write)

This computer is always on anyways and costs like 20 bucks a month or so

## Decision

1. use local compute
2. dockerize everything possible
3. document all env setup

## Consequences

### good
- fast experimentation
- relatively cheaper than cloud-first
- not 
- office gets warm in winter

### bad
- office gets warm in summer
- single point of failure
- limited computational concurrency
- more difficult to track tax-deductible business expenses