```mermaid
---
title: 1.1 Receive Search Request
---
flowchart LR
    ST[start] --> WI{Client<br>side<br>widget}
    WI --> |yes| ET(1.1.1 Event tracking)
    WI --> |no| PS[product search server receives request]
    ET --> PS
    PS --> EN[END]
```
