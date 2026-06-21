# WBS: Hyrox Team Performance Optimizer

La presente Work Breakdown Structure (WBS) traduce i requisiti definiti nella RBS in macro-pacchetti di lavoro (Epiche e Work Packages principali). Dato l'approccio iterativo (Scrum) adottato per il progetto, questa WBS si ferma intenzionalmente a un livello architetturale/strutturale (Livello 2/3). I nodi foglia rappresentano le Epiche e i macro-task che andranno a popolare il Product Backlog e saranno esplosi in User Story durante i singoli Sprint Planning.

**Nota Metodologica sulla Stima Quantitativa (Approccio Ibrido):**
Coerentemente con il framework Scrum, lo sviluppo non seguirà una schedulazione rigida di tipo waterfall. Pertanto, i valori di **Effort (Giorni-Uomo)** e **Durata (Giorni)** indicati in questa WBS rappresentano un'**allocazione preventiva di budget temporale ed economico (Budgetary Estimates)** basata su stime parametriche del team (come il metodo Three-Point). Tali valori servono a definire la baseline dei costi di progetto per giustificare il CapEx iniziale. Durante l'esecuzione, il team utilizzerà metriche puramente agili (Story Points e Velocity) per il monitoraggio e la pianificazione di dettaglio di ciascuno Sprint.


**Livello 0: Progetto Hyrox Team Performance Optimizer**

*   **1. Project Management e Scoping (Fase Conclusa) [Effort: 15 gg-uomo | Durata: 20 gg | Ruoli: PM/PO/TL/DEV]**
    *   1.1 Stesura Specifiche di Dominio
    *   1.2 Definizione Obiettivi e Approccio (CoS, Descrizione dell'Approccio)
    *   1.3 Definizione dei Requisiti (RBS)
    *   1.4 Stesura Project Overview Statement (POS)
    *   1.5 Redazione Analisi dei Rischi e Analisi Finanziaria
    *   1.6 Sviluppo Strutture di Pianificazione (WBS, PDS)
    *   1.7 Gestione e Tracciamento Incontri (Descrizione Meeting)

*   **2. Inizializzazione Tecnica e Gestione Agile [Effort: 17 gg-uomo | Durata: 8 mesi (in parallelo) | Ruoli: PM/TL/DEV/PO]**
    *   2.1 Setup Ambiente di Sviluppo, Repository e pipeline CI/CD [Effort: 5 gg-uomo | Durata: 5 gg | Ruolo: TL]
    *   2.2 Inizializzazione e Gestione Continua Product Backlog [Effort: 4 gg-uomo | Durata: 8 mesi | Ruolo: PO/PM]
    *   2.3 Esecuzione Cerimonie Scrum (Sprint Planning, Daily, Review, Retrospective) [Effort: 8 gg-uomo | Durata: 8 mesi | Ruolo: PM]

*   **3. Design UI/UX e Architettura [Effort: 28 gg-uomo | Durata: 15 gg | Ruoli: TL/DEV/PO]**
    *   3.1 Progettazione Architettura Cloud e Modello Dati [Effort: 6 gg-uomo | Durata: 8 gg | Ruolo: TL]
    *   3.2 Design Interfaccia Utente (UI/UX) Applicazione Smartwatch [Effort: 8 gg-uomo | Durata: 10 gg | Ruolo: DEV]
    *   3.3 Design Interfaccia Utente (UI/UX) Dashboard (Coach e Atleta) [Effort: 10 gg-uomo | Durata: 12 gg | Ruolo: DEV]
    *   3.4 Definizione Protocolli e Sicurezza per la Sincronizzazione Dati [Effort: 4 gg-uomo | Durata: 5 gg | Ruolo: TL]

*   **4. Sviluppo Sottosistema Smartwatch (Wearable) [Effort: 52 gg-uomo | Durata: 35 gg | Ruoli: DEV/TL]** *(Rif. Req. 1 RBS)*
    *   4.1 Implementazione UI Base (Design ad alto contrasto, accessibilità sotto sforzo) [Effort: 8 gg-uomo | Durata: 10 gg | Ruolo: DEV] **(MUST)**
    *   4.2 Sviluppo Logica di Navigazione Allenamento (Skip/Riordina: COULD, Note: MUST) [Effort: 10 gg-uomo | Durata: 12 gg | Ruolo: DEV]
    *   4.3 Sviluppo Modulo Transizione Manuale (Fallback Trigger UI) [Effort: 6 gg-uomo | Durata: 7 gg | Ruolo: DEV] **(MUST)**
    *   4.4 Implementazione Algoritmo Riconoscimento cambio esercizio via Sensori (Gyro/Accel) [Effort: 18 gg-uomo (Three-Point) | Durata: 20 gg | Ruolo: TL] **(MUST)**
    *   4.5 Integrazione Cache Locale (Modalità Offline-First) [Effort: 6 gg-uomo | Durata: 8 gg | Ruolo: DEV] **(SHOULD)**
    *   4.6 Modulo Generazione Report Locale di Fine Sessione (Calcolo Split Times) [Effort: 4 gg-uomo | Durata: 5 gg | Ruolo: DEV] **(MUST)**

*   **5. Sviluppo Sottosistema Dashboard (Smartphone/Web/Tablet) [Effort: 52 gg-uomo | Durata: 40 gg | Ruoli: DEV/PO/TL]** *(Rif. Req. 2 RBS)*
    *   5.1 Sviluppo Modulo Autenticazione e Controllo Accessi (ACL Coach/Atleta) [Effort: 6 gg-uomo | Durata: 7 gg | Ruolo: DEV] **(MUST)**
    *   5.2 Implementazione Gestione Profilo Utente (Soglie cardio, Categoria gara) [Effort: 4 gg-uomo | Durata: 5 gg | Ruolo: DEV] **(MUST)**
    *   5.3 Sviluppo Visualizzazione Comparativa Team (Tabelle Split Times) [Effort: 8 gg-uomo | Durata: 10 gg | Ruolo: DEV] **(MUST)**
    *   5.4 Sviluppo Motore Generazione Grafici di Pacing e Analisi Discrepanze [Effort: 12 gg-uomo | Durata: 15 gg | Ruolo: DEV] **(MUST)**
    *   5.5 Creazione Modulo Inserimento e Gestione Sanzioni/Penalità [Effort: 6 gg-uomo | Durata: 7 gg | Ruolo: DEV] **(MUST)**
    *   5.6 Sviluppo Builder Pianificazione Sessioni (Template esercizi personalizzati e note) [Effort: 10 gg-uomo | Durata: 12 gg | Ruolo: DEV] **(MUST)**
    *   5.7 Integrazione Modalità Offline-Cache per consultazione Dashboard [Effort: 6 gg-uomo | Durata: 8 gg | Ruolo: DEV] **(COULD)**

*   **6. Sviluppo Sottosistema Sincronizzazione [Effort: 26 gg-uomo | Durata: 20 gg | Ruoli: DEV/TL]** *(Rif. Req. 3 RBS)*
    *   6.1 Implementazione Trasferimento Dati Watch -> Smartphone (Connettività locale/Bluetooth) [Effort: 8 gg-uomo | Durata: 10 gg | Ruolo: DEV] **(MUST)**
    *   6.2 Implementazione Sincronizzazione Smartphone -> Cloud/Dashboard (API backend) [Effort: 10 gg-uomo | Durata: 12 gg | Ruolo: DEV/TL] **(MUST)**
    *   6.3 Sviluppo Motore Push Pianificazione (Dashboard -> Smartphone -> Watch) [Effort: 8 gg-uomo | Durata: 10 gg | Ruolo: DEV/TL] **(MUST)**

*   **7. Testing & Quality Assurance [Effort: 36 gg-uomo | Durata: 25 gg | Ruoli: TL/DEV/PM]**
    *   7.1 Unit Testing Componenti Core e API [Effort: 8 gg-uomo | Durata: Continua | Ruolo: DEV]
    *   7.2 Test di Affidabilità e Precisione Algoritmo Sensori (Scenari Hyrox simulati) [Effort: 12 gg-uomo | Durata: 15 gg | Ruolo: TL/DEV]
    *   7.3 Test Usabilità e UI/UX (Obiettivo: SUS Score >= 80/100) [Effort: 6 gg-uomo | Durata: 10 gg | Ruolo: PM/DEV]
    *   7.4 System & Integration Testing (Test end-to-end dei flussi di sincronizzazione) [Effort: 10 gg-uomo | Durata: 12 gg | Ruolo: DEV]

*   **8. Deployment e Rilascio [Effort: 20 gg-uomo | Durata: 15 gg | Ruoli: PM/TL/DEV]**
    *   8.1 Configurazione Infrastruttura Backend di Produzione [Effort: 4 gg-uomo | Durata: 5 gg | Ruolo: TL]
    *   8.2 Preparazione e Rilascio App Wearable (Store specifici) [Effort: 4 gg-uomo | Durata: 5 gg | Ruolo: TL]
    *   8.3 Preparazione e Rilascio App Dashboard (Store / Deploy Web) [Effort: 4 gg-uomo | Durata: 5 gg | Ruolo: DEV]
    *   8.4 Stesura e Revisione Documentazione Tecnica Finale e Manuali Utente [Effort: 8 gg-uomo | Durata: 10 gg | Ruolo: PM/TL/DEV]
