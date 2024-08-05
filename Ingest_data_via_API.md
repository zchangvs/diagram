```mermaid
sequenceDiagram
    Customer->> Catalog API: Insert modify delete pid
    Catalog API ->> Indexing Service: update
    Indexing Service ->> Indexing Queue: pid with metadata
    Indexing Queue ->>  MS PU: pull message and process
    MS PU ->> Global Config: read configuration
    MS PU ->> MS PU : Featurization
    MS PU ->> Catalog Database : update indexing status
    MS PU ->> Vector Database: insert or modify or delete
    end
```
