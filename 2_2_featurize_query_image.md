```mermaid
---
title: 2.2 Featurize query image
---
flowchart LR
    ST[start] --> DS[Download and Store image]
    DS --> MO{Multiple objects detection}
    MO --> |yes| SD(3.2 Single hero object detection)
    MO --> |no| MD(3.3 Multiple objects detection)
    SD --> RO(3.4Recognize Object)
    MD --> RO
    RO -- next object --> RO
    RO --> ED[END] 
