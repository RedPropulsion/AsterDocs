# Spiegazione della configuazione utilizzata nei runner
Il processo di build della documentazione funziona in due step: quando viene fatta una modifica su AsterCPP o una PR, parte in automatico il processo che controlla che le modifiche apportate facciano buildare correttamente.
Viene inoltre generata la documentazione con doxygen, viene trasformata con mkdoxy e pushata qua in AsterDocs per essere integrata con la documentazione generale.

Pushando la documentazione qua parte la fase 2, che compila la documentazione presente su AsterDocs e la pusha su gh pages automaticamente.

```mermaid
---
config:
  theme: mc
  look: classic
---
flowchart TD
 subgraph s1["AsterCPP build runner"]
        n6["cmake build"]
        n7["Doxygen documentation <br>"]
  end
    n3["Modifica su AsterCPP"] --> n7 & n6
    n7 --> n11["check <br>"]
    n6 --> n9["Build successful?"]
    n9 -- No --> n10(["Modifica bloccata <br>"])
    n9 -- Si --> n11
    n11 --> n8["Push to AsterDocs <br>"]
    n6@{ shape: lin-proc}
    n7@{ shape: lin-proc}
    n3@{ shape: rounded}
    n11@{ shape: tri}
    n9@{ shape: diam}
     n10:::Rose
     n10:::Class_01
    classDef Rose stroke-width:1px, stroke-dasharray:none, stroke:#FF5978, fill:#FFDFE5, color:#8E2236
    classDef Class_01 fill:#FFCDD2, stroke:#D50000, stroke-width:1px, stroke-dasharray: 0, color:#000000
    style n10 fill:transparent,color:none
    linkStyle 4 stroke:#D50000,fill:none
    linkStyle 5 stroke:#00C853
```


```mermaid
---
config:
  theme: mc
  look: classic
---
flowchart LR
 subgraph s1["AsterDocs documentation runner"]
        n6["mkbook <br>"]
        n7["mkdoxy <br>"]
  end
    n7 --> n6
    n3["Push su AsterDocs <br>"] --> s1
    s1 --> n8(["Github Pages"])
    n6@{ shape: lin-proc}
    n7@{ shape: lin-proc}
    n3@{ shape: rounded}
    classDef Rose stroke-width:1px, stroke-dasharray:none, stroke:#FF5978, fill:#FFDFE5, color:#8E2236
    classDef Class_01 fill:#FFCDD2, stroke:#D50000, stroke-width:1px, stroke-dasharray: 0, color:#000000

```