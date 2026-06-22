# Release Roadmap

La Release Roadmap definisce la schedulazione temporale dei rilasci e la suddivisione del Product Backlog in cicli iterativi di sviluppo (Sprint). Il progetto si articola su un orizzonte temporale di **8 mesi** suddiviso in **16 Sprint di 2 settimane ciascuno**, raggruppati in 4 fasi principali di rilascio coerenti con le dipendenze logiche e architetturali.

---

## 1. Strategia Generale di Rilascio e Dipendenze

La pianificazione segue una logica di **disaccoppiamento architetturale** e **mitigazione del rischio tecnologico**:
1.  **Fase 1 (Design & Setup):** Setup ambiente, modelli dati e autenticazione. Prima di poter sincronizzare o tracciare, occorre definire come i dati sono strutturati e come i ruoli Coach/Atleta sono protetti.
2.  **Fase 2 (Sviluppo Wearable e Riconoscimento):** Si sviluppa l'app orologio. L'algoritmo ha bisogno di un workout pre-schedulato per funzionare, quindi il builder su dashboard (sviluppato in Fase 1) precede il tracciamento automatico.
3.  **Fase 3 (Analisi Avanzata):** Sviluppo dei grafici di pacing e delle sanzioni sulla dashboard, alimentati dai dati reali sincronizzati.
4.  **Fase 4 (Quality Assurance e Rilascio):** Test end-to-end sul campo, validazione dell'accuratezza e rilascio negli store.

---

## 2. Schedulazione dei 16 Sprint

```mermaid
graph TD
    subgraph Release 1: Foundation (Sprint 1-3)
        S1[Sprint 1: Setup & API] --> S2[Sprint 2: Auth & Profilo] --> S3[Sprint 3: Builder Workout]
    end
    subgraph Release 2: Core Wearable (Sprint 4-8)
        S3 --> S4[Sprint 4: Watch UI & Spike] --> S5[Sprint 5: Push & Fallback] --> S6[Sprint 6: Algo Core] --> S7[Sprint 7: Cache & Reports] --> S8[Sprint 8: Sync Pipeline]
    end
    subgraph Release 3: Advanced Dashboard (Sprint 9-11)
        S8 --> S9[Sprint 9: Team View & Sanctions] --> S10[Sprint 10: Pacing & Flexibility] --> S11[Sprint 11: Offline Dashboard]
    end
    subgraph Release 4: QA & Launch (Sprint 12-16)
        S11 --> S12{Sprint 12: Lab Testing & Gate} --> S13[Sprint 13: Usability & SUS] --> S14[Sprint 14: System E2E] --> S15[Sprint 15: Infra & Store Prep] --> S16[Sprint 16: Deploy & Handover]
    end

    style S12 fill:#ffeb3b,stroke:#f57f17,stroke-width:2px
```

### Fase 1: Inizializzazione e Architettura (Sprint 1 - 3) — *Mesi 1-2*
*Focus:* Definizione delle fondamenta tecniche, sicurezza e protocollo di base.

*   **Sprint 1: Setup Infrastrutturale & Data Modeling (10 SP)**
    *   *User Stories:* US-TEC-01 (Setup CI/CD - 5 SP), US-TEC-02 (Modello Dati e API - 5 SP).
    *   *Obiettivo Sprint:* Repository configurati con pipeline CI/CD attive, schema DB definito e specifiche API Swagger approvate dal Tech Lead per garantire l'allineamento tra gli sviluppatori.
*   **Sprint 2: Sicurezza, ACL e Profilo Utente (8 SP)**
    *   *User Stories:* US-D-01 (Autenticazione e ACL - 5 SP), US-D-02 (Profilazione Atleta e Categoria Gara - 3 SP).
    *   *Obiettivo Sprint:* Flusso di login e registrazione funzionanti, con differenziazione dei ruoli Coach/Atleta a livello di backend e frontend.
*   **Sprint 3: Workout Builder (8 SP)**
    *   *User Stories:* US-D-06 (Builder Workout e Template - 8 SP).
    *   *Obiettivo Sprint:* Il coach può creare workout e salvarli come template su DB.

### Fase 2: Sviluppo Wearable e Riconoscimento Core (Sprint 4 - 8) — *Mesi 3-4*
*Focus:* Sviluppo dell'applicazione smartwatch e dell'algoritmo di tracciamento.

*   **Sprint 4: Watch UI & Spike Riconoscimento Sensori (10 SP)**
    *   *User Stories:* US-W-01 (UI Base ad Alto Contrasto - 5 SP), US-TEC-03 (Spike Tecnologico - Raccolta Dati - 5 SP).
    *   *Obiettivo Sprint:* Layout grafico dello smartwatch pronto per l'uso sotto sforzo. Raccolta delle prime sessioni di dati grezzi da accelerometro/giroscopio per addestrare il modello di riconoscimento.
*   **Sprint 5: Push Protocol & Fallback Trigger (13 SP)**
    *   *User Stories:* US-S-03 (Invio in Push del Workout - 8 SP), US-W-03 (Transizione Manuale - Fallback - 5 SP).
    *   *Obiettivo Sprint:* Implementazione del push del workout allo smartwatch e del fallback manuale tramite gesti fisici sul watch in caso di mancato rilevamento dell'algoritmo.
*   **Sprint 6: Algoritmo Core Riconoscimento (13 SP)**
    *   *User Stories:* US-W-04 (Algoritmo Riconoscimento - Modello Core - 13 SP).
    *   *Obiettivo Sprint:* Prima release stabile dell'algoritmo di tracciamento automatico integrata con la schedulazione.
*   **Sprint 7: Local Storage, Note & Reports (14 SP)**
    *   *User Stories:* US-W-05 (Caching Locale - Offline-First - 8 SP), US-W-02 (Visualizzazione Note Coach - 3 SP), US-W-06 (Report Locale Post-Workout - 3 SP).
    *   *Obiettivo Sprint:* Scrittura continua su cache locale, visualizzazione note coach sul watch e report locale di fine sessione attivo.
*   **Sprint 8: Pipeline Sincronizzazione Dati (10 SP)**
    *   *User Stories:* US-S-01 (Sincronizzazione Bluetooth Watch -> Phone - 5 SP), US-S-02 (Sincronizzazione Phone -> Cloud - 5 SP).
    *   *Obiettivo Sprint:* Trasferimento automatico del file di allenamento dall'orologio al telefono via Bluetooth e successivo upload automatico sul cloud del server dashboard.

### Fase 3: Analisi Avanzata e Flessibilità (Sprint 9 - 11) — *Mesi 5-6*
*Focus:* Sviluppo dei moduli di analisi delle performance e flessibilità d'uso.

*   **Sprint 9: Visualizzazione Team & Gestione Sanzioni (13 SP)**
    *   *User Stories:* US-D-03 (Visualizzazione Comparativa Team - 8 SP), US-D-05 (Gestione Sanzioni / Penalità - 5 SP).
    *   *Obiettivo Sprint:* Tabella comparativa a colonne sulla dashboard del coach e gestione delle sanzioni/no-rep a posteriori con ricalcolo dei tempi.
*   **Sprint 10: Grafici di Pacing & Flessibilità Allenamento (16 SP)**
    *   *User Stories:* US-D-04 (Motore Grafici Pacing - 8 SP), US-W-07 (Skip & Riordina Stazioni su Watch - 8 SP).
    *   *Obiettivo Sprint:* Grafici interattivi di pacing reale vs target sulla dashboard e gestione sul watch delle modifiche all'ordine del workout (skip/riordina).
*   **Sprint 11: Dashboard Offline-First (8 SP)**
    *   *User Stories:* US-D-07 (Dashboard in Modalità Offline - 8 SP).
    *   *Obiettivo Sprint:* Consultazione in sola lettura della dashboard web senza connettività tramite Service Workers ed IndexedDB locale.

### Fase 4: Integrazione, Validazione e Rilascio (Sprint 12 - 16) — *Mesi 7-8*
*Focus:* Testing di sistema su larga scala, validazione scientifica, ottimizzazione e rilascio.

*   **Sprint 12: Lab Testing & Algoritmo Gate (Go/No-Go)**
    *   *Attività:* Test intensivi di precisione e regressione dell'algoritmo (Lab Testing in palestra controllata con 15 coach e 30 atleti).
    *   *Gate Critico (Go/No-Go):* Verifica del criterio di accuratezza ≥ 90%. Se superato, si consolida l'algoritmo. Se fallito, si attiva il **Pivot al Plan B (Manual Trigger)** ottimizzando la UI per la selezione manuale rapida ed eliminando il tracciamento automatico imperfetto.
*   **Sprint 13: Usability & UI/UX Validation**
    *   *Attività:* Test di usabilità sul campo (atleti stressati fisicamente). Calcolo del punteggio SUS.
    *   *Obiettivo Sprint:* Ottenimento di un SUS Score medio ≥ 80/100. Eventuale inserimento di micro-correzioni all'interfaccia smartwatch per facilitare la lettura sotto fatica.
*   **Sprint 14: System Integration & End-to-End Testing**
    *   *Attività:* Test end-to-end sull'intera catena (Dashboard -> Push -> Watch -> Esecuzione -> Bluetooth -> Cloud -> Dashboard). Test di stabilità in caso di caduta connessione.
    *   *Obiettivo Sprint:* Assenza totale di bug critici o bloccanti nell'intero ecosistema.
*   **Sprint 15: Configurazione Infrastruttura & Store Submission**
    *   *Attività:* Setup dell'ambiente di produzione Cloud (AWS/Azure) con configurazioni di sicurezza e scalabilità. Preparazione del pacchetto app ed invio ad Apple App Store Connect per la review.
    *   *Obiettivo Sprint:* App in fase di revisione negli store e backend di produzione pronto e configurato.
*   **Sprint 16: Deployment, Documentazione e Chiusura Progetto**
    *   *Attività:* Rilascio pubblico dell'applicazione web e watchOS. Preparazione del materiale di onboarding per i nuovi clienti (video tutorial su YouTube/Loom, slide di presentazione) e della documentazione tecnica finale per la manutenzione.
    *   *Obiettivo Sprint:* Consegna formale del progetto, Sprint Retrospective finale e chiusura del ciclo di vita del progetto.
