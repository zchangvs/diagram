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
    APP --> |yes| PIU(2.1 Product Insert Update)
    APP --> |no| ED[END]
    PIU --> ED[END] 


```
