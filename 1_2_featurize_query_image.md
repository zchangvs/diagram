```mermaid
---
title: 1.2 Featurize query image
---
flowchart LR
    ST[start] --> RP[load parameters like featureset]
    RP --> DS(1.2.1 Download and Store image)
    DS --> MO{Multiple objects detection}
    MO --> |yes| SD(1.2.2 Single hero object detection)
    MO --> |no| MD(1.2.3 Multiple objects detection)
    SD --> RO(1.2.4 Recognize Object)
    MD --> RO
    RO -- next object --> RO
    RO --> ED[END] 
