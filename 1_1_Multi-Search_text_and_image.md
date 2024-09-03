```mermaid
---
title: Consumer Search with Text and/or Image
---
flowchart TD
%%    ST[start] --> A[query text<br>and/or image]
%%    A --> B{client side<br>widget}
%%    B -->|yes| S(update<br>event tracking)
%%    B --> |no| C[product search<br>server receives request]
    ST[START]--> RSR(Receives search request)
    RSR --> IQ{image?}
    IQ--> |yes| FI(featurize the<br>query image)
    IQ --> |no| TQ{text?}
    FI --> TQ 
    TQ --> |yes| D1(Understand the<br>query text)
    TQ --> |no| E1(find and return result)
    D1 --> E1
%%    D1 --> E1(search for<br>candidates)
%%    E1 --> E2(Rerank & filter logic)
    E1 --> F(Post-processing)
%%    F --> G(update statistics)
    F --> END[END] 


```
