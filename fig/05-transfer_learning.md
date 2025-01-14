```mermaid
flowchart LR
    A[(Dogs & Cats Data)] --> |Train Model| B(Model Dogs & Cats)
    C{Transfer Learning}
    B --> C
    D[(Dog Breeds Data)] --> C
    C --> E(Dog Breeds Model)
```
