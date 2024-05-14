
!!! abstract "Event Flowchart"

    ``` mermaid
    graph LR
      A[Start] --> B{Error?};
      B -->|Yes| C[Hmm...];
      C --> D[Debug];
      D -->|No| E[Yay!];
    ```