```mermaid
---
title: 2. Product Catalog Update
---
flowchart LR
    ST[start] -- connector --> CON[fetch data feed via connector]
    ST -- API --> AP[Insert Update delete API]
    ST -- File fetch --> FF[Parse input file]
    CON --> UP
    AP --> UP
    FF --> UP[Update Product database]
    UP --> APP{Existing App}
    APP --> |yes| IQ[Insert to index queue]
    IQ -- insert/update --> PIU(2.1 Product Insert Update)
    IQ -- delete --> DEL(2.2 Product Delete)
    APP --> |no| ED[END]
    PIU --> ED
    DEL --> ED 


```
