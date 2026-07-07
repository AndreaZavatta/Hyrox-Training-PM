# Agile Communication & Stakeholder Engagement Plan

Il presente documento definisce la strategia di comunicazione e di coinvolgimento degli stakeholder. La comunicazione del progetto è progettata per essere trasparente, frequente ed empirica, eliminando la reportistica tradizionale a favore di cicli di feedback rapidi e dell'ispezione diretta del prodotto.

---

## 1. Governance dei Canali di Comunicazione con gli Stakeholder

Per garantire una collaborazione trasparente ed efficace senza sovraccaricare le attività operative dello Scrum Team, i canali di comunicazione sono strutturati in base alle esigenze dei diversi stakeholder esterni:

*   **TestFlight (Beta Testing):** Al completamento delle milestone principali, gli atleti ricevono la build in formato beta per testarla sul campo, consentendo la raccolta empirica dei dati di usabilità.
*   **Miro:** Utilizzato come spazio visuale condiviso per sessioni di co-design. I coach possono inserire commenti sui wireframe dell'interfaccia utente (UI/UX) della Dashboard Web per ottimizzare la visualizzazione dei grafici di pacing.
*   **E-mail & Stoplight Report:** Canale formale utilizzato a cadenza mensile (ogni 2 Sprint) dal Scrum Master per comunicare l'avanzamento complessivo del progetto tramite report sintetici di status, grafici di Velocity ed evidenziazione dei rischi tecnologici.
*   **Jira & Confluence:** Confluence ospita la documentazione della Roadmap di rilascio e la pianificazione di alto livello visibile a tutti gli stakeholder. Jira funge da repository in cui il Product Owner inserisce e prioritizza le User Story nate direttamente dal feedback degli stakeholder esterni.

---

## 2. Eventi di Sincronizzazione e Touchpoint con gli Stakeholder

La sincronizzazione con gli stakeholder avviene  attraverso touchpoint negli Sprint:

| Touchpoint | Frequenza | Partecipanti Coinvolti | Input Principale | Output Principale | Canale / Modalità |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Sprint Review (Demo Live)** | Ogni 2 settimane (fine Sprint, max 1 ora) | Scrum Team, 15 Coach, Atleti di test | Incremento software funzionante (DoD soddisfatta) | Feedback utente, nuove proposte di requisiti nel backlog | Demo dal vivo del software su smartwatch e Dashboard Web. **No slide.** |
| **Sessioni di Co-Design UI/UX** | fase di design iniziale o refactoring| Product Owner, Tech Lead, Coach | Wireframe su Miro, requisiti utente | Modelli UI approvati, specifiche visive | Lavagna collaborativa virtuale Miro con sessioni asincrone di feedback. |
| **Field Testing & Usability Sync** | Al rilascio delle Milestone (es. Sprint 4, 8, 12) | Scrum Master, Atleti di test | Build beta su TestFlight | Report SUS (System Usability Scale), ticket di anomalia | Distribuzione tramite TestFlight e successiva compilazione di brevi questionari. |
| **Reporting al Board / Investitori** | Mensile (ogni 2 Sprint) | Scrum Master, Board / Investitori | Velocity Chart (Burnup/Burndown), Risk Log | Approvazione dello stato di avanzamento | E-mail formale con allegato Stoplight Report e metriche di performance. |

> [!NOTE]
> Le cerimonie interne del team (come *Sprint Planning*, *Daily Scrum* e *Sprint Retrospective*), incentrate sul coordinamento operativo e sul miglioramento dei processi interni del team, sono escluse da questo piano in quanto riservate esclusivamente allo Scrum Team. Per le loro regole di svolgimento si rimanda ai [Working Agreements](file:///home/zava/Projects/PM-project/Planning/2-working_agreements.md#2-ritmo-di-lavoro-e-cerimonie-scrum).

---

## 3. Matrice di Coinvolgimento degli Stakeholder (Stakeholder Engagement)

Il successo del sistema dipende da una stretta collaborazione con gli utenti finali della palestra partner. La matrice definisce il coinvolgimento dei diversi attori nel ciclo di vita Scrum:

![Matrice di Coinvolgimento degli Stakeholder](../Images/matrice_coinvolgimento_stakeholder.png)

### 3.1 Product Owner (PO)
*   **Ruolo:** Unico punto di contatto per la definizione del valore di business.
*   **Coinvolgimento:** Partecipa attivamente a tutti gli eventi Scrum. Raccoglie i desiderata dei coach esterni e li sintetizza nel Product Backlog. Ha l'autorità esclusiva di accettare le storie completate durante la Sprint Review.

### 3.2 I 15 Coach della Palestra Partner
*   **Ruolo:** Utenti chiave della Dashboard Web.
*   **Coinvolgimento:**
    *   **Sprint Review:** Partecipano come invitati principali ogni 2 settimane per validare i moduli della Dashboard (compilatore di workout, analisi split-times del team, pannello sanzioni).
    *   **Co-Design:** Collaborano asincronamente sulla board Miro durante la fase di design della UI/UX per garantire che i grafici di pacing siano di facile lettura sul campo di allenamento.

### 3.3 I 30 Atleti del Gruppo di Test
*   **Ruolo:** Utenti chiave dell'applicazione Smartwatch e generatori dei dati di telemetria.
*   **Coinvolgimento:**
    *   **Beta Testing (TestFlight):** Ricevono i rilasci dell'app ad ogni conclusione di Sprint (es. al termine dello Sprint 4 per il modulo di navigazione, o dello Sprint 12 per il rilascio finale dell'algoritmo).
    *   **Validazione sul Campo:** Eseguono sessioni di allenamento simulate indossando Apple Watch Series 6+. I loro feedback sull'usabilità dell'interfaccia (es. leggibilità sotto sforzo estremo e utilità del feedback aptico) vengono raccolti tramite brevi questionari e inseriti direttamente come nuove storie nel Backlog.

### 3.4 Board / Investitori
*   **Ruolo:** Organo di controllo e di indirizzo strategico e finanziario del progetto.
*   **Coinvolgimento:**
    *   **Report di Status Mensile:** Al termine di ogni secondo Sprint (mensilmente), il Scrum Master invia un report sintetico contenente la **Velocity del team (Burnup/Burndown chart)** e un breve **Stoplight Report** sullo stato dei rischi critici (in particolare l'accuratezza del classificatore dei sensori).

---

## 4. Ciclo di Feedback Empirico e Adattamento

Il feedback degli stakeholder viene integrato dinamicamente nel ciclo empirico del prodotto:

```
[Demo Funzionante in Sprint Review] 
               │
               ▼
[Feedback di Coach e Atleti]
               │
               ▼
[Scrittura di Nuove User Story / Bug da parte del PO]
               │
               ▼
[Stima del Dev Team in Refinement (Story Points)]
               │
               ▼
[Prioritizzazione nel Product Backlog per lo Sprint Planning successivo]
```

Grazie a questo ciclo continuo di ispezione e adattamento, il sistema "Hyrox Team Performance Optimizer" evolve in base alle reali necessità del campo, garantendo la massima aderenza alle *Conditions of Satisfaction (CoS)* definite all'inizio del progetto.


---

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
