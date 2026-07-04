# **Descrizione dell'Approccio Metodologico**

Questo documento descrive la metodologia che viene adottata per la gestione dell'intero ciclo di vita del progetto "Hyrox Team Performance Optimizer", coprendo tutte le fasi fondamentali del Project Management attraverso il framework **Agile/Scrum**.

---

## **1. Fase di Scoping (Initiating)**

### **1.1 Governance e Partecipanti al Progetto**
La corretta esecuzione del progetto richiede una struttura di governance chiara che bilanci le esigenze di business con la fattibilità tecnica. Di seguito sono definiti i ruoli chiave dello Scrum Team e le relative sfere decisionali:

| Ruolo | Responsabilità Principali | Autorità / Sfera Decisionale |
| :--- | :--- | :--- |
| **Product Owner (PO)** | Massimizzare il Business Value del prodotto. Gestione e prioritizzazione del Product Backlog. Interfaccia con gli stakeholder (coach esterni). | **Cosa sviluppare:** Ha l'ultima parola sulla prioritizzazione delle User Stories e sull'accettazione degli incrementi (DoD). |
| **Scrum Master (SM) / PM** | Facilitare le cerimonie Scrum. Rimuovere gli ostacoli (impediments) segnalati dal team. Garantire il rispetto della metodologia e della governance. | **Processo e Governance:** Decide come facilitare le riunioni e gestisce i rischi finanziari/temporali di macro-livello. |
| **Tech Lead (TL)** | Definire l'architettura tecnica e coordinare il team di sviluppo. Garantire l'integrità concettuale del codice e mitigare i rischi tecnologici. | **Fattibilità Tecnica:** Detiene il potere di veto su requisiti tecnicamente irrealizzabili o ad alto rischio architetturale. |
| **Dev Team (Core Team)** | Sviluppare gli incrementi di prodotto. Effettuare le stime in Story Points. Garantire la qualità del codice tramite test e peer review. | **Come sviluppare:** Ha completa autonomia sulle scelte di implementazione e sulla stima dello sforzo dei task. |

### **1.2 Protocollo di Escalation delle Decisioni**
In caso di conflitto decisionale o impossibilità di raggiungere il consenso entro 60 minuti, si attiva il protocollo di escalation in 3 livelli:
* **Livello 1 (Facilitazione SM/PM):** Lo Scrum Master / PM faciliterà una sessione di consensus building focalizzata (max 60 minuti).
* **Livello 2 (Arbitrato per Dominio):** Il Tech Lead deciderà sui conflitti tecnologici/architetturali, il Product Owner sulle priorità di business, lo Scrum Master / PM sui rischi finanziari e temporali.
* **Livello 3 (Escalation Esecutiva):** Decisioni o conflitti che impattano >15% del budget o >20% della timeline vengono revisionati formalmente dal CEO.
* **Regola Aurea:** Le decisioni tecniche non potranno essere sovrascritte da richieste di business; il Tech Lead avrà potere di veto su requisiti tecnicamente irrealizzabili.

### **1.3 Processo di Scoping Meeting**
Il *Project Scoping Meeting* non è un evento isolato, ma un processo di confronto iterativo. Per mantenere velocità decisionale, si prediligono sessioni di lavoro facilitate e consensus building, documentando le decisioni in verbali formali (es. Verbale #01).

### **1.4 Deliverable di Scoping**
Durante questa fase vengono prodotti i seguenti artefatti:
* **Conditions of Satisfaction (CoS):** Strutturate da WANTS a NEEDS, prioritizzate con metodo MoSCoW.
* **Requirements Breakdown Structure (RBS):** Scomporrà i requisiti in feature misurabili, fungendo da ponte logico verso la scomposizione del backlog (WBS).
* **Project Overview Statement (POS):** Definirà il problem statement, l'obiettivo e i criteri di successo quantitativi.

---

## **2. Fase di Planning**

La fase di pianificazione è progettata per garantire l'allineamento tra gli obiettivi strategici definiti nello Scoping e l'esecuzione operativa.

### **2.1 Project Definition Statement (PDS)**
L’avvio della fase di pianificazione è sancito dal passaggio formale dal POS al PDS. Il PDS espande i contenuti del POS, stabilendo gli obiettivi strategici, la governance e la cornice metodologica per lo sviluppo dell'ecosistema, includendo le attività definite nell'RBS e l'analisi empirica dei rischi.

### **2.2 Work Breakdown Structure (WBS)**
Partendo dalla RBS, si costruisce la **Work Breakdown Structure (WBS)**. Questo strumento organizza gerarchicamente i requisiti di prodotto (in Epiche, Feature e User Story) per garantire l'integrità concettuale dello sviluppo, includendo stime in **Story Points (SP)** (scala di Fibonacci) e pianificazione guidata dalla **Velocity** del team.

### **2.3 Backlog e Pianificazione Iterativa**
Le componenti della WBS vengono tradotte in un *Product Backlog* ordinato. Le dimensioni delle User Story sono stimate in Story Points tramite *Planning Poker* dal Dev Team. Per mitigare l'incertezza tecnologica ed effettuare la validazione precoce del modello di riconoscimento dei movimenti, viene inserito uno *Spike* nello Sprint 4, finalizzato alla raccolta preliminare di dati sensori (accelerometro/giroscopio).

### **2.4 Release Roadmap e Baseline dei Costi**
Il piano temporale è rappresentato tramite una Release Roadmap che mappa le macro-fasi su un orizzonte temporale fisso di **8 mesi (16 Sprint di 2 settimane ciascuno)**, garantendo visibilità agli stakeholder. La *Cost Baseline* viene definita calcolando il Burn Rate del team, definendo le curve dei costi operativi per il controllo del Cash Flow.

### **2.5 Strumenti di Monitoraggio (Sprint Board)**
La gestione operativa avviene tramite *Sprint Board* (Jira), dove le attività evolvono negli stati (To Do, In Progress, Code Review/Test, Done). La *Definition of Done (DoD)* e la *Definition of Ready (DoR)* assicurano che ogni incremento soddisfi gli standard qualitativi e di processo prima del rilascio.

---

## **3. Fase di Launching & Execution**

### **3.1 Modello di Staffing e Organizzazione del Team**
Durante la fase esecutiva, il team opera come uno **Scrum Team** auto-organizzato e cross-funzionale. Per definire chiaramente i ruoli operativi, contrattuali e decisionali, le risorse umane del progetto sono classificate secondo la tassonomia metodologica di Wysocki:
*   **Co-Project Manager (Developer):** Lo Scrum Master / PM, con responsabilità sulla schedula, sul budget, sui rischi e sulla governance del processo Scrum.
*   **Co-Project Manager (Client):** Il Product Owner, interfaccia con il business, responsabile della definizione dei requisiti e della validazione finale dei rilasci.
*   **Core Team:** Gli sviluppatori e specialisti stabili che possiedono le competenze verticali chiave necessarie a garantire l'integrità concettuale dell'architettura.
*   **Developer Team:** Sviluppatori di supporto allocati per lo sviluppo verticale (backend, database, testing e QA).
*   **Client Team:** Stakeholder e utilizzatori finali (come coach e atleti del gruppo di test) incaricati di fornire feedback qualitativi e validare l'usabilità.
*   **Contracted Team:** Eventuali consulenti o partner esterni contrattualizzati su specifiche attività ad alta specializzazione (non previsti se le competenze interne sono sufficienti).

### **3.2 Bilanciamento del Team (Learning Styles di David Kolb)**
Per ottimizzare la collaborazione e mitigare il "Bus Factor", il team viene strutturato e bilanciato coprendo le quattro dimensioni del modello di David Kolb per le attitudini e gli stili di apprendimento:
*   **Assimilating (Modelli Teorici):** Focalizzato sulla progettazione logica, l'analisi dei dati di avanzamento e la modellazione teorica dell'algoritmo.
*   **Converging (Applicazione Pratica):** Orientato alla risoluzione di problemi tecnologici complessi, programmazione sistematica e implementazione dell'architettura.
*   **Diverging (Ideazione e UX):** Centrato sulla visualizzazione dei problemi da prospettive multiple, fondamentale per il co-design della UI/UX e della visualizzazione dati.
*   **Accommodating (Azione sul Campo):** Orientato al testing empirico a contatto con gli utenti finali, al superamento degli ostacoli d'integrazione e all'adattamento rapido ai cambiamenti.

### **3.3 Matrice RASCI Operativa Generale**
Le responsabilità sulle principali macro-attività della fase di esecuzione sono tracciate mediante la seguente matrice RASCI di alto livello:

| Macro-Attività / Fasi WBS | Scrum Master (SM) / PM | Tech Lead (TL) | Product Owner (PO) | Dev Team (DEV) |
| :--- | :---: | :---: | :---: | :---: |
| **1. Project Management e Scoping** | **A** / **R** | **C** | **C** | **I** |
| **2. Inizializzazione Tecnica & Agile** | **A** | **R** | **I** | **R** |
| **3. Design UI/UX & Architettura** | **I** | **A** / **R** | **C** | **R** |
| **4. Sviluppo Sottosistema Smartwatch** | **I** | **A** | **C** | **R** |
| **5. Sviluppo Sottosistema Dashboard** | **I** | **A** | **C** | **R** |
| **6. Sviluppo Sottosistema Sincronizzazione** | **I** | **A** / **R** | **I** | **R** |
| **7. Testing & Quality Assurance** | **A** | **R** | **C** | **R** |
| **8. Deployment e Rilascio** | **I** | **R** | **A** | **R** |

*Legenda: **R** = Responsible, **A** = Accountable, **C** = Consulted, **I** = Informed.*

### **3.4 Knowledge Management Strategy**
Per mitigare i rischi legati a competenze esclusive (Bus Factor) e preservare l'integrità concettuale dell'architettura:
*   **Pair Programming:** Applicato su attività ad alta complessità algoritmica o di integrazione.
*   **Documentazione di Progetto:** Redazione sistematica di docstrings nel codice e schemi architetturali (es. modello C4) all'interno del Project Workbook condiviso.
*   **Sessioni di Allineamento Tecnico:** Incontri periodici dedicati alla condivisione interna delle soluzioni e al trasferimento tecnologico tra i membri del team.

### **3.5 Regole Operative del Team (Working Agreements)**
La governance operativa adotta Working Agreements strutturati per gestire il processo decisionale, la risoluzione di blocchi e la comunicazione:
*   **Decision Making & Consensus:**
    *   *Stile decisionale:* Si predilige uno stile *collaborativo/partecipativo* per le decisioni di architettura e design dei dati, e uno stile *consultivo/direttivo* in capo al Product Owner per la prioritizzazione strategica del backlog.
    *   *Avviso di Wysocki sul Consensus:* Si riconosce che la ricerca forzata di un compromesso indebolisce le decisioni. In caso di stallo oltre un limite temporale prefissato (es. 60 minuti), si attiva l'escalation per dominio: Tech Lead per conflitti tecnici, PO per conflitti di business, PM per vincoli di budget/tempo.
*   **Problem Solving & Conflict Resolution:**
    *   *Problem Solving:* Si stabilisce l'adozione di un modello metodologico strutturato (come il **modello a 5 passi di Daniel Couger**) per definire, analizzare, proporre, selezionare e validare le azioni correttive sui problemi bloccanti.
    *   *Conflict Resolution:* Risoluzione dei conflitti tecnici tramite negoziazione cooperativa ed empatia (*Collaborating/Integrating*), mitigando comportamenti competitivi (*Competing*) o evitanti (*Avoiding*).
*   **Brainstorming Method:** Riunioni mirate dei tecnici di riferimento, sospensione di giudizi critici durante la generazione libera di idee, e test mentale delle alternative per convergere sulla soluzione ottimale.
*   **Gestione delle Riunioni (Meeting Management):**
    *   *Prima del meeting:* PM/SM verifica la necessità dell'incontro, ne definisce chiaramente lo scopo e invia l'agenda in anticipo convocando solo le risorse essenziali.
    *   *Durante il meeting:* Rispetto rigoroso dei timebox, focus sugli obiettivi senza digressioni personali, e utilizzo di supporti visivi e board.
    *   *Dopo il meeting:* Stesura immediata di *Action Items* con responsabili e scadenze, pubblicazione del verbale e pianificazione preliminare del meeting successivo.
*   **Tipologie di Meeting Standard:**
    1.  *Daily Status:* Breve incontro quotidiano timeboxato (es. 15 minuti) incentrato sullo status operativo dei task (On Track, Ahead, Behind) e sull'emersione di impedimenti, con esclusione di discussioni tecniche.
    2.  *Problem Resolution Meeting:* Incontri operativi mirati per risolvere i blocchi identificati durante il Daily Status.
    3.  *Project Review Meeting:* Dimostrazione del software funzionante (DoD soddisfatta) a fine Sprint per raccogliere feedback da Sponsor, Coach e utenti finali.

### **3.6 Gestione delle Risorse, Saturazione e Livellamento**
*   **Resource Loading (Focus Factor 75%):** Per evitare l'over-allocation invisibile, la pianificazione giornaliera adotta un focus factor del 75% della capacità produttiva dedicata a compiti della WBS. La restante parte (25%) è allocata all'overhead organizzativo e alle cerimonie Scrum (Daily, Review, planning, code review e documentazione).
*   **Strategie di Resource-Leveling:**
    1.  *Utilizzo degli Slack:* Ritarare l'avvio di task non critici con margini di scorrimento positivi per liberare ore in favore di task sul percorso critico.
    2.  *Rimodulazione della Durata:* Diluire lo sforzo giornaliero di un task critico su più giorni lavorativi se lo sforzo stimato è superiore al previsto.
    3.  *Sostituzione e Supporto (Resource Substitution):* Riassegnazione temporanea di risorse cross-funzionali per supportare membri del team su task bloccanti.
    4.  *Straordinario Controllato (Overtime):* Considerato come ultima risorsa, regolamentato entro una soglia percentuale massima e autorizzato dal PM esclusivamente per la protezione di milestone critiche di rilascio.

---

## **4. Fase di Monitoring & Controlling**

### **4.1 Status Meetings e Reporting Stratificato**
* **Issue Log e Daily Standup:** Monitoraggio dei task aperti a livello operativo quotidiano.
* **Sprint Review & Demo Live:** Riunioni di fine Sprint (ogni 2 settimane, max 1 ora) in cui lo Scrum Team presenta un incremento software funzionante (DoD soddisfatta) a coach e atleti per raccogliere dei feedback.
* **Reporting:** Variance Report bi-settimanali, Release Roadmap per la visione macroscopica, Sprint Board/Burn-up per il micro-management iterativo, e Stoplight Report mensile (ogni 2 Sprint) per il Board / Investitori.

### **4.2 Monitoraggio Performance**
Il monitoraggio avviene tramite Velocity Tracking (Story Points completati / Sprint), Burndown Chart e progressione dell'Accuracy dell'algoritmo.

### **4.3 Gestione Dinamica del Backlog e Scope Bank**
Il cambiamento viene gestito attraverso una **Scope Bank** supportata da una Time Contingency Reserve pari al 10% della durata del progetto (gestita come buffer nei cicli di Sprint) e da una Budget Contingency Reserve di €24.700. In ottica Scrum, i nuovi requisiti diventano User Story stimate dal Dev Team in Story Points e inserite nel Product Backlog dal Product Owner.
* **Gestione del Vincolo (Fixed Capacity):** Poiché le risorse e la durata del progetto (8 mesi, 16 Sprint) sono fisse, l'inserimento di una nuova User Story ad alta priorità comporta che il PO rimuova o posticipi dal backlog elementi di pari sforzo (in Story Points), tipicamente a priorità COULD o SHOULD.

### **4.4 Protocolli di Validazione e Contingency**
* **Validation Protocol:** La validazione empirica avviene tramite *Lab Testing* (simulazioni di movimento controllate in palestra eseguite dal Tech Lead) e *Field Testing* (condizioni di gara reali con i 30 atleti del gruppo di test), raccogliendo i dati di usabilità tramite il questionario standardizzato SUS (System Usability Scale) con target di SUS Score ≥ 80/100.
* **Go/No-Go Protocol (Gate Critico):** Al completamento della validazione dell'algoritmo nello Sprint 12, se l'accuratezza non raggiungerà la soglia minima del 90%, si attiverà il **Pivot al Plan B (Manual Trigger)**. In questo scenario, si esclude il tracciamento automatico e ci si basa interamente sulla transizione manuale rapida tramite fallback trigger (US-W-03) con interfaccia ottimizzata.

---

## **5. Fase di Closing**

A completamento dello sviluppo e dei test, il progetto entrerà nella fase formale di chiusura.

### **5.1 Post-Implementation Audit**
Verrà condotto un audit finale per verificare oggettivamente il raggiungimento dei Success Criteria definiti nel POS/PDS:
* Accuratezza dell'algoritmo confermata ≥ 90% (se non attivato il Plan B).
* Discrepanza del tempo rilevato rispetto al cronometro ufficiale < 2%.
* SUS Score di usabilità ≥ 80/100 (raccolto dai 15 coach e 30 atleti).
* Tempo medio di editing per coach ridotto sotto i 2 minuti nel 95% delle sessioni.

### **5.2 Executive / Internal Sign-off**
Verrà organizzato un *Project Readiness Review* con il Product Owner (o Board) per presentare i risultati dell'audit. L'accettazione finale dei deliverable per il rilascio commerciale avverrà tramite un'approvazione formale interna (Executive Sign-off) che attesterà la conclusione della fase di sviluppo core (Sprint 16) e l'avvio della fase di post-lancio (fuori perimetro progetto).

### **5.3 Lessons Learned e Archiviazione**
* **Knowledge Transfer:** Verrà eseguita una *Knowledge Transfer Checklist*, organizzando una sessione di onboarding formativa (con presentazione di supporto) per i nuovi clienti e fornendo un video tutorial esplicativo (YouTube) accompagnato da una guida di avvio rapido (Quick Start Guide).
* **Lessons Learned:** Lo Scrum Master / PM condurrà una sessione di retrospettiva globale con lo Scrum Team per redigere il documento di *Lessons Learned*, identificando cosa ha funzionato e cosa andrà migliorato nei futuri progetti.
* **Archiviazione:** Tutta la documentazione (POS, PDS, Product Backlog, Log dei Cambiamenti, Verbali e Retrospective) verrà congelata e archiviata centralmente.
