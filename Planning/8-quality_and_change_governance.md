# Quality & Change Governance

Il presente documento definisce le regole di governance per la gestione della **Qualità** e dello **Scope (Cambiamenti)**. Il controllo di qualità e l'adattamento dello scope si basano sul controllo empirico del processo, gestito attraverso la *Definition of Done (DoD)*, la *Definition of Ready (DoR)* e la prioritizzazione continua del *Product Backlog*.

---

## 1. Gestione Empirica dei Cambiamenti (Scope Control)

In Scrum, il cambiamento è accolto come opportunità per massimizzare il valore del prodotto. Non esistono "Change Request Forms" o "Change Control Boards". Lo scope è governato esclusivamente attraverso il **Product Backlog Refinement** sotto la diretta responsabilità del Product Owner (PO):

```
       [Nuova Esigenza]
(Coach, Atleti o feedback da Test)
              │
              ▼
    [Creazione User Story]
   (Aggiunta nel Backlog dal PO)
              │
              ▼
   [Stima in Story Points]
 (Dev Team durante il Refinement)
              │
              ▼
 [Valutazione e Ordinamento]
(PO decide la priorità nel Backlog)
              │
              ▼
     [Sprint Planning]
(Inserimento nello Sprint se prioritario)
```

### 1.1 Regole per l'Inserimento di Nuovi Requisiti
1.  **Autorità del Product Owner:** Solo il PO ha l'autorità di aggiungere, rimuovere o modificare l'ordine degli elementi nel Product Backlog.
2.  **Stima del Dev Team:** Nessun elemento può essere inserito in uno Sprint senza essere stato precedentemente stimato in Story Points dal Dev Team.
3.  **Gestione del Vincolo Temporale ed Economico (Fixed Capacity):** Poiché le risorse e la durata totale del progetto (8 mesi, 16 Sprint) sono fisse, l'inserimento di una nuova User Story ad alta priorità comporta necessariamente la ri-prioritizzazione del backlog. Il PO dovrà rimuovere o posticipare elementi di pari sforzo (in Story Points) posizionati in fondo al backlog (tipicamente le storie marcate come `COULD` o `SHOULD`).

---

## 2. Governance della Qualità (Quality Control)

La qualità del software viene garantita a livello di processo attraverso due filtri fondamentali: la **Definition of Ready (DoR)** e la **Definition of Done (DoD)**.

### 2.1 Definition of Ready (DoR) - Criteri di Ingresso dello Sprint
Una User Story è considerata "Pronta" per essere inserita nello Sprint Planning solo se soddisfa tutti i criteri della DoR (acronimo **INVEST**):
*   **I**ndependent: La storia è autonoma e può essere sviluppata senza blocchi esterni.
*   **N**egotiable: I dettagli implementativi sono flessibili e negoziabili tra PO e Dev Team.
*   **V**aluable: Porta un valore di business chiaro e misurabile a Coach o Atleti.
*   **E**stimable: Il Dev Team possiede abbastanza dettagli per stimarla in Story Points.
*   **S**mall: È dimensionata per essere completata comodamente entro un singolo Sprint (in genere <= 8 Story Points).
*   **T**estable: Ha criteri di accettazione chiari ed oggettivi.

### 2.2 Definition of Done (DoD) - Criteri di Rilascio dell'Incremento
Nessuna User Story può essere considerata "Completata" (Done) e presentata nella Sprint Review se non rispetta rigorosamente la seguente DoD:

#### Sviluppo & Standard di Codice
*   Il codice è compilato con successo su watchOS (Wearable) e Web/Node (Dashboard) senza warning critici.
*   Il codice segue le linee guida architetturali concordate (MVC/MVVM) e la convenzione dei commit.
*   È stata eseguita una sessione di **Peer Review** (almeno un approvatore su Pull Request).

#### Testing & Copertura
*   La suite di Unit Test è stata eseguita con successo nella pipeline CI/CD.
*   Il codice di business logic (algoritmo di calcolo, logica di sync, controlli ACL) ha un **Code Coverage minimo dell'80%**.
#### Integrazione & Validazione
*   Il feature branch è stato correttamente fuso (merged) nel branch `review` dopo approvazione del Tech Lead.
*   L'app per smartwatch è stata distribuita con successo su **TestFlight** per il testing interno degli atleti.
*   Il PO ha testato la funzionalità in ambiente di staging e ha confermato il soddisfacimento dei criteri di accettazione della storia.

---

## 3. Strategia di Testing Empirico sul Campo

Dato il contesto ad alta intensità fisica (allenamento Hyrox), la qualità non si limita alla correttezza del codice, ma si estende all'usabilità e all'accuratezza dei sensori:

```
[Sviluppo Codice & Unit Test] ──> [CI/CD Automated Integration] ──> [Rilascio TestFlight]
                                                                            │
                                                                            ▼
[Validazione Usabilità (SUS)] <── [Test sul Campo (30 Atleti)] <── [Test in Lab (Simulato)]
```

*   **Test in Laboratorio (Lab Testing):** Per validare l'algoritmo di riconoscimento degli esercizi (US-W-04), il Tech Lead esegue simulazioni di movimento controllate per stabilire una baseline di accuratezza ed eliminare i falsi positivi (es. confusione tra Sled Push e Sled Pull).
*   **Test sul Campo (Field Testing):** Sotto la supervisione del Scrum Master, i 30 atleti eseguono workout Hyrox completi in condizioni di affaticamento reale per testare l'app.
*   **Validazione Usabilità (SUS Score):** Al termine dei rilasci delle milestone principali (Sprint 4, Sprint 8, Sprint 12), viene somministrato agli atleti e ai coach il questionario **System Usability Scale (SUS)**. L'obiettivo qualitativo di Sprint è il raggiungimento di un **SUS Score >= 80/100**. Punteggi inferiori generano automaticamente task di refactoring dell'interfaccia nel backlog.

---

## 4. Gestione del Debito Tecnico e Refactoring

Per evitare il degrado della qualità del software (entropia del codice) a lungo termine, il team adotta la seguente politica di gestione del debito tecnico:
*   **Allocazione Fissa di Capacità:** In ogni Sprint Planning, il team alloca fino al **10-15% della Velocity stimata** alla risoluzione del debito tecnico e al refactoring.
*   **Tracciamento nel Backlog:** Il debito tecnico non viene nascosto; viene formalizzato in *Technical Stories* o *Technical Tasks* inseriti nel Product Backlog (es. "Ottimizzazione allocazione memoria watchOS per telemetria prolungata").
*   **Refactoring Continuo:** Piccoli refactoring vengono eseguiti continuamente come parte dello sviluppo delle storie quotidiane, nel rispetto della regola dello *Scout* ("lascia il codice migliore di come lo hai trovato").
