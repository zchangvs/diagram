```mermaid
---
title: consumer search with both text and image
---
flowchart TD
    ST[start] --> A[query text<br>and/or image]
    A --> B{client side<br>widget}
    B -->|yes| S(update<br>event tracking)
    B --> |no| C[product search<br>server receives request]
    S --> C
    C --> TQ{text?}
    TQ--> |yes| D1(Understand the<br>query text)
    C --> IQ{image?}
    IQ--> |yes| D2(featurize the<br>query image)
    D1 --> E1(search for<br>candidates)
    D2 --> E1
    TQ--> |no| E1
    IQ--> |no| E1 
    E1 --> E2(apply rerank & filter logic)
    E2 --> F[return result]
    F --> G(update statistics)
    G --> END[END] 


```
