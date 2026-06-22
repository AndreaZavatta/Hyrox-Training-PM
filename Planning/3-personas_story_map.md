# User Personas & User Story Mapping

Il presente documento definisce le **User Personas** (i profili dei destinatari chiave del sistema) e lo **User Story Mapping** (la mappatura delle funzionalità rispetto all'esperienza utente e alle release di progetto), stabilendo un legame chiaro tra le necessità reali degli utenti e le specifiche operative del Product Backlog.

---

## 1. User Personas

Per guidare le scelte di usabilità (UI/UX) e architettura, sono stati identificati due profili utente principali, rappresentativi delle macro-categorie di stakeholder del sistema.

### Persona 1: Roberto, il Coach (Head Coach & Owner)

*   **Dati Demografici:** 38 anni, ex-atleta di cross-training, proprietario e Head Coach di un box affiliato Hyrox con oltre 45 atleti attivi.
*   **Ruolo nel Progetto:** Amministratore della piattaforma. Crea i workout, pianifica le sessioni per le classi (singoli o gruppi di 2 o 4), monitora i progressi e applica penalità/sanzioni in base ai no-rep effettivi degli atleti.
*   **Obiettivi & Bisogni:**
    *   **Efficienza Operativa:** Ridurre il tempo di inserimento dei dati post-allenamento da 15 minuti a meno di 2 minuti.
    *   **Analisi dei Pacing:** Ottenere report visivi immediati che confrontano le performance degli atleti sulle stazioni funzionali (SkiErg, Row, Wall Balls, ecc.) per individuare le debolezze di ognuno.
    *   **Gestione delle Sanzioni:** Poter correggere a posteriori o in tempo reale le penalità degli atleti per garantire l'accuratezza dei tempi totali.
*   **Frustrazioni & Punti di Dolore:**
    *   Spreco di tempo nel registrare manualmente split times e no-rep su tabelle cartacee o fogli Excel.
    *   Difficoltà a visualizzare e confrontare l'andamento storico del team per pianificare strategie di pacing di gara personalizzate.

### Persona 2: Marco, l'Atleta (Competitore Master)

*   **Dati Demografici:** 32 anni, impiegato aziendale, atleta Hyrox categoria "Master 30-34" con 4 allenamenti settimanali ad alta intensità.
*   **Ruolo nel Progetto:** Utente finale del sistema orologio (Wearable) e consumatore dei report personali sulla dashboard (smartphone/web).
*   **Obiettivi & Bisogni:**
    *   **Lettura ad Alto Sforzo:** Visualizzare metriche chiave (Frequenza Cardiaca, tempo split, note coach) sullo schermo dell'orologio ad occhio nudo, anche con una frequenza cardiaca superiore a 170 bpm.
    *   **Interazione Zero-Touch:** Completare l'intera sessione Hyrox senza dover interagire fisicamente con lo schermo dell'orologio.
    *   **Feedback Immediato:** Ricevere feedback (vibrazione) al cambio stazione.
*   **Frustrazioni & Punti di Dolore:**
    *   Smartwatch che non rilevano correttamente le stazioni o che richiedono tocchi continui sullo schermo bagnato di sudore.
    *   Perdita o corruzione dei dati memorizzati sul watch a causa di disconnessioni bluetooth o batterie scariche.
    *   Mancanza di flessibilità quando la palestra è affollata e gli attrezzi sono occupati, venendo costretto a interrompere il tracciamento o a saltare blocchi di lavoro.

---

## 2. Lo User Story Mapping (La Matrice)

Lo User Story Mapping organizza il Product Backlog su due dimensioni:
1.  **L'Asse Orizzontale (The Backbone):** Mappa la user journey sequenziale (l'esperienza utente dell'atleta e del coach dall'inizio alla fine di una sessione).
2.  **L'Asse Verticale (The Releases):** Mappa la priorità di rilascio, suddividendo le User Story in tre Release progressive (in linea con la `release_roadmap.md`).

### Le 6 Fasi della User Journey (Backbone)
*   **Fase 1: Configurazione Profilo & Accessi:** L'atleta configura il suo profilo personale (soglie cardiache, categoria) e vengono impostati gli accessi/ACL sul database.
*   **Fase 2: Creazione & Programmazione Workout:** Il coach crea l'allenamento tramite il Workout Builder definendo le stazioni e gli atleti coinvolti.
*   **Fase 3: Invio & Ricezione:** Il workout pianificato viene inviato in push e caricato sullo smartwatch per l'avvio della sessione.
*   **Fase 4: Esecuzione & Tracciamento:** L'atleta esegue l'allenamento monitorando i dati su display e ricevendo feedback in tempo reale dall'algoritmo.
*   **Fase 5: Sincronizzazione Dati:** I dati della sessione fluiscono dal watch allo smartphone e poi al database cloud.
*   **Fase 6: Debriefing & Analisi:** Coach e atleta analizzano i grafici, confrontano i pacing del team e correggono eventuali penalità.

---

### La Matrice di Mapping

| User Journey -> <br> Release | 1. Configurazione Profilo & Accessi | 2. Creazione & Programmazione Workout | 3. Invio & Ricezione | 4. Esecuzione & Tracciamento | 5. Sincronizzazione Dati | 6. Debriefing & Analisi |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| **RELEASE 1 (MVP)<br>Core Ecosistema**<br>*Sprints 1-8*<br>*(Effort: 86 SP)* | **US-TEC-01** (Setup CI/CD/Repo)<br>**US-TEC-02** (Architettura DB/API)<br>**US-D-01** (Autenticazione e ACL)<br>**US-D-02** (Profilo & Categoria) | **US-D-06** (Workout Builder) | **US-S-03** (Push Workout a Watch)<br>**US-W-02** (Note Coach su Watch) | **US-W-01** (UI Watch Alto Contrasto)<br>**US-TEC-03** (Spike Raccolta Dati)<br>**US-W-03** (Fallback Manuale)<br>**US-W-04** (Algoritmo Riconoscimento) | **US-W-05** (Caching Watch Offline)<br>**US-S-01** (Sync Watch->Phone)<br>**US-S-02** (Sync Phone->Cloud) | **US-W-06** (Report Finale su Watch) |
| **RELEASE 2<br>Advanced Analytics & Flexibility**<br>*Sprints 9-11*<br>*(Effort: 37 SP)* | - | - | - | **US-W-07** (Skip & Riordina Stazioni) | **US-D-07** (Dashboard Offline-First) | **US-D-03** (Tabella Comparativa Team)<br>**US-D-05** (Gestione Sanzioni/Penalità)<br>**US-D-04** (Grafici di Pacing) |

---

## 3. Allineamento con le Personas (Giustificazione del Mapping)

*   **Perché la Release 1 (MVP) copre l'intero percorso utente core?**  
    Per essere considerato un vero *Minimum Viable Product*, il sistema deve permettere l'esecuzione end-to-end dell'allenamento. Roberto (il Coach) deve poter definire la struttura del workout tramite il builder (Fase 2) e inviarlo all'orologio dell'atleta (Fase 3). Marco (l'Atleta) deve poter avviare la sessione, tracciarla (tramite algoritmo `US-W-04` o fallback manuale `US-W-03` in caso di elevata fatica) e sincronizzare i dati (Fase 5) per visualizzare il report locale (Fase 6). Questa unione (Sprints 1-8) garantisce che la prima release distribuita agli utenti sia effettivamente utilizzabile sul campo per raccogliere feedback reali.
*   **Perché le Sanzioni, i Grafici di Pacing e la flessibilità sono in Release 2?**  
    Queste funzionalità avanzate rispondono al bisogno di Roberto (il Coach) di effettuare debriefing storici sul team. Esse richiedono un volume di dati reali già sincronizzati per generare grafici significativi e consentire il confronto a 4 colonne tra gli atleti. Inoltre, la funzionalità di riordino e skip sul watch (`US-W-07`) e la visualizzazione offline della dashboard (`US-D-07`) rappresentano ottimizzazioni dell'esperienza utente che consolidano il prodotto ma non sono bloccanti per l'avvio del tracciamento core.
