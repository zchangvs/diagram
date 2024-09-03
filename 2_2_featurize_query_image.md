```mermaid
---
title: 2.2 Featurize query image
---
flowchart LR
    ST[start] --> DS[Download and Store image]
    DS --> MO{Multiple objects detection}
    MO --> |yes| SD[Single hero object detection]
    MO --> |no| MD[Multiple objects detection]
    SD --> RO[Recognize Object]
    MD --> RO
    RO -- next object --> RO
    RO --> ED[END] 
