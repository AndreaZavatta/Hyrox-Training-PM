# User Personas & User Story Mapping: Hyrox Team Performance Optimizer

Il presente documento definisce le **User Personas** (i profili dei destinatari chiave del sistema) e lo **User Story Mapping** (la mappatura delle funzionalità rispetto all'esperienza utente e alle release di progetto), stabilendo un legame chiaro e scientifico tra le necessità reali degli utenti e le specifiche operative del Product Backlog.

---

## 1. User Personas

Per guidare le scelte di usabilità (UI/UX) e architettura, sono stati identificati due profili utente principali, rappresentativi delle macro-categorie di stakeholder del sistema.

### Persona 1: Roberto, il Coach (Head Coach & Owner)

*   **Dati Demografici:** 38 anni, ex-atleta di cross-training, proprietario e Head Coach di un box affiliato Hyrox con oltre 45 atleti attivi.
*   **Ruolo nel Progetto:** Amministratore della piattaforma. Crea i workout, pianifica le sessioni per le classi, monitora i progressi e applica penalità/sanzioni in base ai no-rep effettivi degli atleti.
*   **Obiettivi & Bisogni:**
    *   **Efficienza Operativa:** Ridurre il tempo di inserimento dei dati post-allenamento da 15 minuti a meno di 2 minuti.
    *   **Analisi dei Pacing:** Ottenere report visivi immediati che confrontano le performance degli atleti sulle stazioni funzionali (SkiErg, Row, Wall Balls, ecc.) per individuare le debolezze di ognuno.
    *   **Gestione delle Sanzioni:** Poter correggere a posteriori o in tempo reale le penalità degli atleti per garantire l'accuratezza dei tempi totali.
*   **Frustrazioni & Punti di Dolore:**
    *   Spreco di tempo nel registrare manualmente split times e no-rep su tabelle cartacee o fogli Excel.
    *   Discrepanze e discussioni con gli atleti riguardo al conteggio delle ripetizioni e delle penalità applicate durante i circuiti affollati.
    *   Difficoltà a visualizzare e confrontare l'andamento storico del team per pianificare strategie di pacing di gara personalizzate.

### Persona 2: Marco, l'Atleta (Competitore Master)

*   **Dati Demografici:** 32 anni, impiegato aziendale, atleta Hyrox categoria "Master 30-34" con 4 allenamenti settimanali ad alta intensità.
*   **Ruolo nel Progetto:** Utente finale del sistema orologio (Wearable) e consumatore dei report personali sulla dashboard (smartphone/web).
*   **Obiettivi & Bisogni:**
    *   **Lettura ad Alto Sforzo:** Visualizzare metriche chiave (Frequenza Cardiaca, tempo split, note coach) sullo schermo dell'orologio ad occhio nudo, anche con una frequenza cardiaca superiore a 170 bpm.
    *   **Interazione Zero-Touch:** Completare l'intera sessione Hyrox senza dover interagire fisicamente con lo schermo dell'orologio (impossibile con sudore o guanti).
    *   **Feedback Immediato:** Ricevere riscontri fisici forti (vibrazione) per i no-rep segnalati o al cambio stazione.
*   **Frustrazioni & Punti di Dolore:**
    *   Smartwatch che non rilevano correttamente le stazioni o che richiedono tocchi continui sullo schermo bagnato di sudore.
    *   Perdita o corruzione dei dati memorizzati sul watch a causa di disconnessioni bluetooth o batterie scariche.
    *   Mancanza di flessibilità quando la palestra è affollata e gli attrezzi sono occupati, venendo costretto a interrompere il tracciamento o a saltare blocchi di lavoro.

---

## 2. Lo User Story Mapping (La Matrice)

Lo User Story Mapping organizza il Product Backlog su due dimensioni:
1.  **L'Asse Orizzontale (The Backbone):** Mappa la user journey sequenziale (l'esperienza utente dell'atleta e del coach dall'inizio alla fine di una sessione).
2.  **L'Asse Verticale (The Releases):** Mappa la priorità di rilascio, suddividendo le User Story in tre Release progressive (in linea con la `release_roadmap.md`).

### Le 5 Fasi della User Journey (Backbone)
*   **Fase 1: Configurazione & Assegnazione:** Il coach crea l'allenamento e l'atleta configura il suo profilo (soglie cardiache, categoria).
*   **Fase 2: Invio & Ricezione:** Il workout viene inviato in push e caricato sullo smartwatch per la sessione.
*   **Fase 3: Esecuzione & Tracciamento:** L'atleta esegue l'allenamento monitorando i dati su display e ricevendo feedback in tempo reale.
*   **Fase 4: Sincronizzazione Dati:** I dati fluiscono dal watch allo smartphone e poi al database cloud del backend.
*   **Fase 5: Debriefing & Analisi:** Coach e atleta analizzano i grafici, confrontano i pacing e correggono eventuali sanzioni/penalità.

---

### La Matrice di Mapping

| User Journey -> <br> Release | 1. Configurazione & Assegnazione | 2. Invio & Ricezione | 3. Esecuzione & Tracciamento | 4. Sincronizzazione Dati | 5. Debriefing & Analisi |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **RELEASE 1<br>Foundation (MVP)**<br>*Sprints 1-3*<br>*(Effort: 26 SP)* | **US-TEC-01** (Setup CI/CD/Repo)<br>**US-TEC-02** (Architettura DB/API)<br>**US-D-01** (Autenticazione e ACL)<br>**US-D-02** (Profilo & Categoria)<br>**US-D-06** (Workout Builder) | - | - | - | - |
| **RELEASE 2<br>Core Wearable**<br>*Sprints 4-8*<br>*(Effort: 60 SP)* | - | **US-S-03** (Push Workout a Watch)<br>**US-W-02** (Note Coach su Watch) | **US-W-01** (UI Watch Alto Contrasto)<br>**US-TEC-03** (Spike Raccolta Dati)<br>**US-W-03** (Fallback Manuale)<br>**US-W-04** (Algoritmo Riconoscimento) | **US-W-05** (Caching Watch Offline)<br>**US-S-01** (Sync Watch->Phone)<br>**US-S-02** (Sync Phone->Cloud) | **US-W-06** (Report Finale su Watch) |
| **RELEASE 3<br>Advanced & Polish**<br>*Sprints 9-11*<br>*(Effort: 37 SP)* | - | - | **US-W-07** (Skip & Riordina Stazioni) | **US-D-07** (Dashboard Offline-First) | **US-D-03** (Tabella Comparativa Team)<br>**US-D-05** (Gestione Sanzioni/Penalità)<br>**US-D-04** (Grafici di Pacing) |

---

## 3. Allineamento con le Personas (Giustificazione del Mapping)

*   **Perché la Release 1 si concentra sulla Configurazione?**  
    Roberto (il Coach) deve poter definire la struttura del workout prima che l'atleta possa sincronizzarla o tracciarla. Inoltre, senza la profilazione delle soglie cardiache e delle categorie di Marco (l'Atleta), i calcoli di intensità e pesistica non avrebbero un benchmark di riferimento.
*   **Perché l'Algoritmo Core e il Fallback Manuale sono in Release 2?**  
    Risponde alla frustrazione primaria di Marco (l'Atleta) di non dover toccare lo schermo durante lo sforzo estremo. Nel caso in cui il sensore non rilevi una transizione in un ambiente affollato o caotico, la presenza contemporanea di `US-W-03` (Fallback con Crown + tasto laterale per 1s) garantisce a Marco la sicurezza di non perdere il tracciamento, mitigando il rischio tecnologico.
*   **Perché le Sanzioni e il Pacing Comparativo sono in Release 3?**  
    Queste funzionalità avanzate rispondono al bisogno di Roberto (il Coach) di effettuare debriefing storici sul team. Esse richiedono un volume di dati reali già sincronizzati (abilitati dalle pipeline di Release 2) per generare grafici significativi e consentire il confronto accurato a 4 colonne tra gli atleti.
