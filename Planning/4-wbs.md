# Work Breakdown Structure (WBS) / Scomposizione del Backlog

Il progetto adotta una **Work Breakdown Structure (WBS)**. Questo documento organizza gerarchicamente i requisiti di prodotto per garantire l'integrità concettuale dello sviluppo includendo stime in **Story Points (SP)** (scala di Fibonacci) e inserendo la pianificazione guidata dalla **Velocity** del team.


## Livello 0: Product Goal
Sviluppare un ecosistema integrato (Wearable App + Web Dashboard) per ottimizzare la pianificazione, il monitoraggio in gara e l'analisi post-allenamento dei team Hyrox, riducendo il tempo operativo dei coach ed eliminando il carico cognitivo dell'atleta.

---

## Livello 1: Epiche, Feature e User Story

### EPIC 1: Sottosistema Smartwatch (Wearable) [Totale: 47 SP]
*Focus:* Sviluppo dell'applicazione nativa watchOS per l'acquisizione dei dati sul campo.

*   **Feature 1.1: Interfaccia Utente (UI) & Navigazione [11 SP]**
    *   **US-W-01 (UI Base ad Alto Contrasto) [5 SP] (MUST):** Schermate ad altissimo contrasto per facilitare la lettura dei dati biometrici e del pacing sotto stress fisico estremo.
    *   **US-W-02 (Visualizzazione Note Coach) [3 SP] (MUST):** Visualizzazione a schermo delle direttive e dei pesi associati alla stazione attiva del workout.
    *   **US-W-06 (Report Locale Post-Workout) [3 SP] (MUST):** Visualizzazione sul watch a fine sessione dei tempi di split delle 8 stazioni e dei tempi di transizione (Roxzone).
*   **Feature 1.2: Algoritmo di Riconoscimento Esercizi [18 SP]**
    *   **US-W-04 (Algoritmo Riconoscimento - Modello Core) [13 SP] (MUST):** Classificatore inerziale che distingue in modo automatico la corsa (Roxzone) dalle stazioni di forza (Sled, Lunge, Burpee, ecc.).
    *   **US-TEC-03 (Spike Tecnologico - Acquisizione Dati Sensori) [5 SP] (MUST):** Raccolta preliminare di campioni accelerometrici per addestrare e validare il modello di riconoscimento.
*   **Feature 1.3: Flessibilità & Transizione Manuale [18 SP]**
    *   **US-W-03 (Fallback Trigger Manuale) [5 SP] (MUST):** Funzionalità di transizione manuale tramite gesti rapidi/pulsanti fisici se l'algoritmo fallisce il riconoscimento automatico.
    *   **US-W-07 (Skip & Riordina Stazioni su Watch) [13 SP] (COULD):** Possibilità per l'atleta di saltare o riordinare gli esercizi se un macchinario in palestra è occupato.

---

### EPIC 2: Sottosistema Dashboard (Web Portal) [Totale: 45 SP]
*Focus:* Portale di configurazione e analisi delle performance del team.

*   **Feature 2.1: Profilazione, Sicurezza & ACL [8 SP]**
    *   **US-D-01 (Autenticazione e Controllo Accessi ACL) [5 SP] (MUST):** Accesso differenziato: il Coach visualizza e analizza l'intero team; l'Atleta visualizza le proprie sessioni ed ha permessi di scrittura limitati alle sanzioni.
    *   **US-D-02 (Profilazione Fisiologica e Gara) [3 SP] (MUST):** Memorizzazione delle zone di frequenza cardiaca e della categoria ufficiale Hyrox (Open, Pro, Double, Relay).
*   **Feature 2.2: Pianificatore Workout (Builder) [8 SP]**
    *   **US-D-06 (Builder Workout e Template) [8 SP] (MUST):** Interfaccia a blocchi per strutturare la sequenza degli esercizi e salvarli come template riutilizzabili.
*   **Feature 2.3: Monitoraggio Performance & Analisi Team [21 SP]**
    *   **US-D-03 (Visualizzazione Comparativa Team) [8 SP] (MUST):** Tabella split times comparativa a colonne per i 4 atleti del team post-allenamento.
    *   **US-D-04 (Motore Grafici di Pacing Overlay) [8 SP] (MUST):** Grafici interattivi che sovrappongono l'andatura reale dell'atleta rispetto alla baseline pianificata.
    *   **US-D-05 (Inserimento e Gestione Sanzioni/Penalità) [5 SP] (MUST):** Interfaccia per inserire no-rep e penalità di tempo con ricalcolo immediato della classifica.
*   **Feature 2.4: Offline Dashboard [8 SP]**
    *   **US-D-07 (Dashboard in Modalità Offline) [8 SP] (COULD):** Visualizzazione locale dei dati di performance pre-ciclati in assenza di connessione internet.

---

### EPIC 3: Sottosistema Sincronizzazione Dati [Totale: 21 SP]
*Focus:* Protocolli di comunicazione a bassa latenza e architettura Offline-First.

*   **Feature 3.1: Bluetooth & Local Sync [5 SP]**
    *   **US-S-01 (Sincronizzazione Bluetooth Watch -> Phone) [5 SP] (MUST):** Trasferimento automatico e locale del file telemetrico dall'Apple Watch allo smartphone a fine sessione.
*   **Feature 3.2: API Cloud Sync [8 SP]**
    *   **US-S-02 (Sincronizzazione Phone -> Cloud) [8 SP] (MUST):** Upload del workout dallo smartphone al server cloud per l'aggiornamento immediato della Dashboard.
*   **Feature 3.3: Push Protocol [8 SP]**
    *   **US-S-03 (Invio in Push del Workout) [8 SP] (MUST):** Invio automatico del workout pianificato dalla Dashboard allo smartwatch dell'atleta (tempo target < 10 secondi).

---

### EPIC 4: Inizializzazione Tecnica & Gestione Agile [Totale: 13 SP]
*Focus:* Supporto architetturale e infrastruttura di continuous integration.

*   **Feature 4.1: Setup CI/CD & Infrastruttura [5 SP]**
    *   **US-TEC-01 (Setup Repository e Pipeline CI/CD) [5 SP] (MUST):** Configurazione degli ambienti e dei flussi di build automatizzati per watchOS e Web.
*   **Feature 4.2: Data Modeling Core [8 SP]**
    *   **US-TEC-02 (Progettazione Modello Dati e API Core) [8 SP] (MUST):** Definizione dello schema database e dei contratti API per garantire la coerenza dei dati tra i sottosistemi.

---

## 2. Note Metodologiche sulla Stima e Pianificazione

1.  **Story Points vs Ore/Giorni:** Gli Story Points sono assegnati dal Dev Team e rappresentano la complessità complessiva, lo sforzo e l'incertezza tecnica di ciascuna User Story (scala di Fibonacci: 3, 5, 8, 13).
2.  **Pianificazione degli Sprint (Velocity):** Con una Velocity stimata del team pari a circa **8-10 Story Points per Sprint**, il backlog complessivo di **126 SP** è schedulato per essere sviluppato in circa 13 Sprint di puro sviluppo, lasciando i restanti Sprint per la validazione sul campo (SUS, Lab Testing) e il rilascio finale.
3.  **Gestione del Debito Tecnico:** Le attività di refactoring e manutenzione non sono inserite in questa scomposizione di business, ma vengono stimate come storie tecniche aggiuntive all'inizio di ogni Sprint Planning (fino al 15% della capacità dello Sprint).
