```mermaid
---
title: 2.3 Understand query text
---
flowchart LR
    ST[START] --> CNER{Name Entity Recognition}
    CNER --> |yes| NER(3.6 NER processing)
    CNER --> |no| TF(3.7 tokenization and featurization)
    NER --> TF
    TF --> ED[END] 
