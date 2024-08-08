```mermaid
title MultiSearch indexing
flowchart TD
    Start[start] --> IS[Indexing Service<br>receives request]
    IS --> IQ[Insert the request to queue]
    PU[Production Understanding pulls a request] --> IQ
    PU --> GC[Global Config read System and Customer App configuration]
    PU --> FE{Featurization needed?}
    FE--> |yes| AG[Algorithm worker create vectors]
    FE--> |no| UM[update MS database]
    AG --> UM
    UM --> VB[update vector DB]
```
