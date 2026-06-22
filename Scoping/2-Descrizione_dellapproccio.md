# **Descrizione dell'Approccio Metodologico**

Questo documento descrive la metodologia che **verrà adottata** per la gestione dell'intero ciclo di vita del progetto "Hyrox Team Performance Optimizer", coprendo tutte le fasi fondamentali del Project Management.

---

## **1. Fase di Scoping (Initiating)**

### **1.1 Governance e Partecipanti al Progetto**
La corretta esecuzione del progetto richiederà una struttura di governance chiara che bilanci le esigenze di business con la fattibilità tecnica. Di seguito sono definiti i ruoli chiave coinvolti nelle decisioni metodologiche:

| Ruolo | Responsabilità |
| :--- | :--- |
| **Project Manager (PM)** | Facilitatore del processo, Garante della conformità metodologica, Gestore del tempo e delle risorse. |
| **Developer Co-PM (Tech Lead)** | Responsabile della fattibilità tecnica, Valutazione dei rischi tecnologici (algoritmo), Architettura tecnica e Code review. |
| **Product Owner** | Definizione degli obiettivi di business, Validazione delle *Conditions of Satisfaction*, Approvazione delle priorità. |
| **Core Team Tecnico** | Stime operative (Three-Point, Planning Poker), Analisi vincoli implementativi, Supporto costruzione RBS e WBS. |

### **1.2 Protocollo di Escalation delle Decisioni**
In caso di conflitto decisionale, il processo di escalation seguirà questa gerarchia:
* **Livello 1 (Facilitazione PM):** Il PM faciliterà una sessione di consensus building (max 60 minuti).
* **Livello 2 (Arbitrato per Dominio):** Il Tech Lead deciderà sui rischi tecnici, il Product Owner sulle priorità di business, il PM sui rischi finanziari.
* **Livello 3 (Escalation Esecutiva):** Richiesta per decisioni che impattano >15% del budget o 20% della timeline tramite Project Management Review.
* **Regola Aurea:** Le decisioni tecniche non potranno essere sovrascritte da richieste di business; il Tech Lead avrà potere di veto su requisiti tecnicamente irrealizzabili.

### **1.3 Processo di Scoping Meeting**
Il *Project Scoping Meeting* non sarà un evento isolato, ma un processo di confronto iterativo. Per mantenere velocità decisionale, si prediligeranno sessioni di lavoro facilitate e consensus building, documentando le decisioni in verbali formali (es. Verbale #01).

### **1.4 Deliverable di Scoping**
Durante questa fase verranno prodotti i seguenti artefatti:
* **Conditions of Satisfaction (CoS):** Strutturate da WANTS a NEEDS, prioritizzate con metodo MoSCoW.
* **Requirements Breakdown Structure (RBS):** Scomporrà i requisiti in feature misurabili, fungendo da ponte logico verso la WBS.
* **Project Overview Statement (POS):** Definirà il problem statement, l'obiettivo e i criteri di successo quantitativi.

---

## **2. Fase di Planning**

La fase di pianificazione sarà progettata per garantire l'allineamento tra gli obiettivi strategici definiti nello Scoping e l'esecuzione operativa.

### **2.1 Project Definition Statement (PDS)**
L’avvio della fase di pianificazione sarà sancito dal passaggio formale dal POS al PDS. Il PDS espanderà i contenuti del POS, includendo le attività definite nell'rbs e l'analisi dei rischi, per avere una visione di insieme del progetto in fase di planning.

### **2.2 Work Breakdown Structure (WBS)**
Partendo dalla RBS, si costruirà la **Work Breakdown Structure (WBS)**. La WBS fungerà da *Planning Tool* e *Architectural Design Tool*, garantendo che il lavoro operativo sia la traduzione esatta dei requisiti approvati. Ogni Work Package verrà mappato su specifiche User Story.

### **2.3 Backlog e Pianificazione Iterativa**
Le componenti della WBS verranno tradotte in un *Product Backlog* e prioritizzate. Le dimensioni delle User Story saranno stimate in Story Points tramite *Planning Poker*. Per mitigare l'incertezza tecnologica, verrà inserito uno *Spike* nelle prime iterazioni, finalizzato alla produzione di un PoC.

### **2.4 Release Roadmap e Baseline dei Costi**
Il piano temporale sarà rappresentato tramite una Release Roadmap, che mapperà le macro-fasi garantendo visibilità agli stakeholder. La *Cost Baseline* verrà definita calcolando il Burn Rate del team, definendo le curve dei costi operativi per il controllo del Cash Flow.

### **2.5 Strumenti di Monitoraggio (Sprint Board)**
La gestione operativa avverrà tramite *Sprint Board* (Jira), dove le attività evolveranno negli stati (To Do, In Progress, Test, Done). La *Definition of Done (DoD)* assicurerà che ogni incremento rispetti gli standard di qualità.

---

## **3. Fase di Launching & Execution**

### **3.1 Team Organization e Matrice RASCI**
Il team opererà con una struttura a Team Dedicato (Projectized) e Cross-funzionale. I ruoli saranno definiti da una matrice RASCI con un solo Accountable per task per evitare sovrapposizioni e garantire la tracciabilità delle responsabilità. I task complessi o sul Critical Path verranno formalizzati in Work Packages con chiari criteri di accettazione.

| Macro-Attività / Fasi WBS | Project Manager (PM) | Tech Lead (TL) | Product Owner (PO) | Core Team Tecnico (DEV) |
| :--- | :---: | :---: | :---: | :---: |
| **1. Project Management e Scoping** | **A** / **R** | **C** | **C** | **I** |
| **2. Inizializzazione Tecnica & Agile** | **A** | **R** | **I** | **R** |
| **3. Design UI/UX & Architettura** | **I** | **A** / **R** | **C** | **R** |
| **4. Sviluppo Sottosistema Smartwatch** | **I** | **A** | **C** | **R** |
| **5. Sviluppo Sottosistema Dashboard** | **I** | **A** | **C** | **R** |
| **6. Sviluppo Sottosistema Sincronizzazione** | **I** | **A** / **R** | **I** | **R** |
| **7. Testing & Quality Assurance** | **A** | **R** | **C** | **R** |
| **8. Deployment e Rilascio** | **A** | **R** | **R** | **I** |

*Legenda: **R** = Responsible (Esecutore), **A** = Accountable (Responsabile ultimo), **C** = Consulted (Consultato), **I** = Informed (Informato).*


### **3.2 Knowledge Management Strategy**
Per mitigare il 'Bus Factor' (rischio legato a competenze specifiche su watchOS e ML), si implementeranno:
* **Pair Programming:** Obbligatorio su task critici.
* **Documentazione Obbligatoria:** Docstrings e diagrammi C4 per l'architettura.
* **Knowledge Sharing Sessions:** 1 ora settimanale per il trasferimento di competenze interne.

### **3.3 Team Operating Rules**
* **Daily Standup:** 15 minuti rigidi focalizzati sullo status (On Track, Ahead, Behind); gli ostacoli verranno delegati all'Issue Log.
* **Problem Solving (5 Step):** Definizione, Raccolta dati, Root Cause Analysis (5 Whys), Brainstorming, Piano d'azione.

---

## **4. Fase di Monitoring & Controlling**

### **4.1 Status Meetings e Reporting Stratificato**
* **Issue Log e Daily Standup:** Monitoraggio dei task aperti a livello operativo quotidiano.
* **Project Review Meetings:** Riunioni legate alle milestone per le Go/No-Go decisions.
* **Reporting:** Variance Report bi-settimanali, Release Roadmap per la visione macroscopica e Sprint Board/Burn-up per il micro-management iterativo, Stoplight Report mensile per il Senior Management.

### **4.2 Monitoraggio Performance**
Il monitoraggio avverrà tramite Velocity Tracking (Story Points completati / Sprint), Burndown Chart e progressione dell'Accuracy dell'algoritmo.

### **4.3 Gestione Dinamica del Backlog e Scope Bank**
Il cambiamento verrà gestito attraverso una **Scope Bank** supportata da una Time Contingency Reserve pari al 10% della durata del progetto e da una Budget Contingency Reserve di €11.000. In ottica Agile, i nuovi requisiti non passeranno per moduli burocratici, ma diventeranno nuove User Story che il Product Owner inserirà nel Product Backlog.
* **Stima e Negoziazione:** Le nuove richieste saranno stimate usando il Three-Point Method o lo Story Pointing. Per aggiungere una nuova feature senza impattare budget o tempo, il Product Owner dovrà "depositare" giorni rimuovendo feature a priorità 'COULD', concordando la ri-prioritizzazione.

### **4.4 Protocolli di Validazione e Contingency**
* **Validation Protocol:** La validazione empirica avverrà tramite *Lab Testing* (palestra controllata) e *Field Testing* (condizioni di gara reali).
* **Go/No-Go Protocol:** Al completamento della validazione del PoC, se l'algoritmo non raggiungerà il 90% di accuratezza, si attiverà un 'Pivot to Plan B', ovvero il passaggio a una modalità "Full Manual". In questo scenario, il tracciamento si baserà interamente sull'utilizzo del 'Manual Trigger' (funzionalità già prevista nello scope per gestire i casi limite), abbandonando l'uso dell'algoritmo automatico.

---

## **5. Fase di Closing**

A completamento dello sviluppo e dei test, il progetto entrerà nella fase formale di chiusura.

### **5.1 Post-Implementation Audit**
Verrà condotto un audit finale per verificare oggettivamente il raggiungimento dei Success Criteria definiti nel POS:
* Accuratezza dell'algoritmo confermata ≥ 90%.
* Discrepanza del tempo rilevato rispetto al cronometro ufficiale < 2%.
* SUS Score di usabilità ≥ 80/100.
* Tempo medio di editing per coach ridotto sotto i 2 minuti.

### **5.2 Executive / Internal Sign-off**
Verrà organizzato un *Project Readiness Review* con il Product Owner (o Board) per presentare i risultati dell'audit. L'accettazione finale dei deliverable per il rilascio commerciale avverrà tramite un'approvazione formale interna (Executive Sign-off) che attesterà la conclusione della fase di sviluppo core e l'avvio della fase di iterazione post-lancio (fuori perimetro progetto).

### **5.3 Lessons Learned e Archiviazione**
* **Knowledge Transfer:** Verrà eseguita una *Knowledge Transfer Checklist*, consegnando ai coach i manuali d'uso della dashboard e l'App Wearable.
* **Lessons Learned:** Il PM condurrà una sessione di retrospettiva globale con il team tecnico per redigere il documento di *Lessons Learned*, identificando cosa ha funzionato e cosa andrà migliorato nei futuri progetti.
* **Archiviazione:** Tutta la documentazione (POS, PDS, Log delle CR, Verbali) verrà congelata e archiviata centralmente.

