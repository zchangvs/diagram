```mermaid
---
title: 1.3 Understand query text
---
flowchart LR
    ST[START] --> CNER{Name Entity Recognition}
    CNER --> |yes| NER(1.3.1 NER processing)
    CNER --> |no| TF(1.3.2 tokenization and featurization)
    NER --> TF
    TF --> ED[END] 
