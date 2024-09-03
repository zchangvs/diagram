```mermaid
---
title: 2.2 Featurize query image
---
flowchart LR
    ST[start] --> RP[load parameters like featureset]
    RP --> DS(3.2 Download and Store image)
    DS --> MO{Multiple objects detection}
    MO --> |yes| SD(3.3 Single hero object detection)
    MO --> |no| MD(3.4 Multiple objects detection)
    SD --> RO(3.5 Recognize Object)
    MD --> RO
    RO -- next object --> RO
    RO --> ED[END] 
