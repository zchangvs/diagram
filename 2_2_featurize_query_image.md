```mermaid
---
title: 2.2 Featurize query image
---
flowchart LR
    ST[start] --> DS[Download and Store image]
    DS --> MO{Multiple objects detection}
    MO --> yes| 
