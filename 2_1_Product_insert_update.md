```mermaid
---
title: 2.1 Product Insert and Update
---
flowchart LR
    ST[START] --> PQ[Pull request from Queue]
    PQ -- next request --> PQ
    PQ --> RC[Read Global and App Config]
    RC --> PU(2.1.1 Production Understanding)
    PU --> CU[Update Product Catalog]
    PU --> VD[Vector DB update]
    VD --> REP[Replicate data to deployments]
    REP --> ED[END]
    CU --> ED
```
