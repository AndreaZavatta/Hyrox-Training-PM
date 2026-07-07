# Schede di Dettaglio dei Work Packages (WP) - Copertura Completa WBS

Questo documento organizza l'intero Product Backlog (128 SP) in **6 Work Packages (WP) strutturati**, garantendo la scomposizione e la copertura al 100% di tutte le Epiche e User Story definite nella WBS.

> [!NOTE]
> **Giustificazione dell'Approccio Globale:**
> I Work Packages sono tipicamente utilizzati in modo selettivo per i task sul percorso critico, ad alto rischio o complessi. Adottando una metodologia ibrida, abbiamo scelto di mappare l'**intero backlog** in 6 macro Work Packages (coincidenti con le Epiche del nostro Product Backlog) come strumento di controllo amministrativo di alto livello e tracciabilità verso gli stakeholder esterni, fermo restando che l'esecuzione avviene interamente tramite sprint backlog ed eventi Scrum. Il focus dello Scrum Master e del Tech Lead nella compilazione e nel monitoraggio delle schede si concentra primariamente sui WP critici:
> * **WP 2 (Smartwatch App UI & Cache)** e **WP 3 (Algoritmo ML & Roxzone):** identificati come i package a maggior rischio tecnologico e posizionati sul percorso critico.
> * **WP 6 (Sync Bluetooth/Cloud):** a causa della complessità di integrazione tra i diversi canali di sincronizzazione dati.

---

## Indice dei Work Packages
*   **WP 1 (Epic 4):** Inizializzazione Tecnica, Infrastruttura CI/CD e Modello Dati Core
*   **WP 2 (Epic 1):** Sviluppo App Wearable (Interfaccia, Caching Locale & Fallback Manuale)
*   **WP 3 (Epic 1):** Algoritmo di Riconoscimento Automatico & Flessibilità Gara
*   **WP 4 (Epic 2):** Web Dashboard (Profilazione, Sicurezza & Workout Builder)
*   **WP 5 (Epic 2):** Modulo Analytics (Grafici di Pacing, Tabella Comparativa & Sanzioni)
*   **WP 6 (Epic 3):** Protocolli di Sincronizzazione Locale (Bluetooth) e Cloud (APNs)

---

## WP 1: Inizializzazione Tecnica, Infrastruttura CI/CD e Modello Dati Core

*   **Riferimento WBS:** Epic 4 (Inizializzazione Tecnica & Gestione Agile)
*   **User Stories Associate:** US-TEC-01 (Setup Repository e CI/CD) [5 SP], US-TEC-02 (Progettazione Modello Dati e API Core) [5 SP]
*   **Responsabile del WP:** Giovanni Manca (Tech Lead)
*   **Risorse Assegnate:** Giovanni Manca (Tech Lead), Matteo Neri (Backend Developer)
*   **Sforzo Stimato:** 10 Story Points

### Obiettivo e Attività Principali
L'obiettivo è realizzare l'architettura dei dati (schema database) e l'infrastruttura CI/CD per abilitare lo sviluppo parallelo. Le attività comprendono:
1.  Setup dei repository Git e branch protetti.
2.  Configurazione pipeline CI/CD (GitHub Actions) per test e build.
3.  Progettazione dello schema ER del database.
4.  Definizione dei contratti API (OpenAPI/Swagger).

---

## WP 2: Sviluppo App Wearable (Interfaccia, Caching Locale & Fallback)

*   **Riferimento WBS:** Epic 1 (Sottosistema Smartwatch) - Feature 1.1, 1.3 (in parte), 1.4
*   **User Stories Associate:** US-W-01 (UI Base) [5 SP], US-W-02 (Note Coach) [3 SP], US-W-03 (Fallback Manuale) [5 SP], US-W-05 (Caching Locale) [8 SP], US-W-06 (Report Locale) [3 SP]
*   **Responsabile del WP:** Luca Rossi (Senior Wearable Developer)
*   **Risorse Assegnate:** Luca Rossi (Senior Wearable Developer), Sara Viola (Mobile Developer / QA)
*   **Sforzo Stimato:** 24 Story Points

### Obiettivo e Attività Principali
Realizzare l'applicazione nativa per Apple Watch focalizzandosi sulla leggibilità sotto stress fisico, caching locale e transizione manuale. Le attività comprendono:
1.  Sviluppo UI nativa watchOS (SwiftUI) ad alto contrasto.
2.  Integrazione notifiche aptiche per i cambi stazione.
3.  Implementazione database locale (CoreData/SQLite) per uso offline.
4.  Sviluppo modulo di fallback manuale tramite tasti fisici.

---

## WP 3: Algoritmo di Riconoscimento Automatico & Flessibilità Gara

*   **Riferimento WBS:** Epic 1 (Sottosistema Smartwatch) - Feature 1.2, 1.3 (in parte)
*   **User Stories Associate:** US-TEC-03 (Spike Acquisizione Sensori) [5 SP], US-W-04 (Modello Core Algoritmo) [13 SP], US-W-07 (Skip & Riordina Stazioni) [13 SP]
*   **Responsabile del WP:** Giovanni Manca (Tech Lead & ML Specialist)
*   **Risorse Assegnate:** Giovanni Manca (Tech Lead & ML Specialist), Luca Rossi (Senior Wearable Developer), Sara Viola (Mobile Developer)
*   **Sforzo Stimato:** 31 Story Points

### Obiettivo e Attività Principali
Sviluppare il classificatore per il cambio automatico delle stazioni e le transizioni (Roxzone), integrando la flessibilità di riordino. Le attività comprendono:
1.  Raccolta dati inerziali tramite Spike tecnico.
2.  Addestramento modello di riconoscimento basato su CoreMotion.
3.  Integrazione logica di Skip/Riordino stazioni dall'orologio.

---

## WP 4: Web Dashboard (Profilazione, Sicurezza & Workout Builder)

*   **Riferimento WBS:** Epic 2 (Sottosistema Dashboard) - Feature 2.1, 2.2, 2.4
*   **User Stories Associate:** US-D-01 (Auth & ACL) [5 SP], US-D-02 (Profilazione Fisiologica) [3 SP], US-D-06 (Builder Workout) [8 SP], US-D-07 (Dashboard Offline) [8 SP]
*   **Responsabile del WP:** Elena Bianchi (Senior Frontend Developer)
*   **Risorse Assegnate:** Elena Bianchi (Senior Frontend Developer), Matteo Neri (Backend Developer)
*   **Sforzo Stimato:** 24 Story Points

### Obiettivo e Attività Principali
Sviluppare la piattaforma web comprendente autenticazione, gestione schede e pianificazione workout. Le attività comprendono:
1.  Sviluppo frontend React con autenticazione JWT e ruoli (Coach/Atleta).
2.  Creazione del Workout Builder visivo.
3.  Integrazione parametri e pesi ufficiali dal rulebook Hyrox.
4.  Configurazione PWA per il caricamento offline.

---

## WP 5: Modulo Analytics (Grafici di Pacing, Tabella Comparativa & Sanzioni)

*   **Riferimento WBS:** Epic 2 (Sottosistema Dashboard) - Feature 2.3
*   **User Stories Associate:** US-D-03 (Visualizzazione Comparativa Team) [8 SP], US-D-04 (Motore Grafici di Pacing Overlay) [8 SP], US-D-05 (Gestione Sanzioni/Penalità) [5 SP]
*   **Responsabile del WP:** Elena Bianchi (Senior Frontend Developer)
*   **Risorse Assegnate:** Elena Bianchi (Senior Frontend Developer), Matteo Neri (Backend Developer / Data Analyst)
*   **Sforzo Stimato:** 21 Story Points

### Obiettivo e Attività Principali
Implementare il motore analitico per visualizzare i dati del team e confrontare le performance. Le attività comprendono:
1.  Sviluppo grafici interattivi (pacing overlay) per l'analisi comparativa.
2.  Creazione tabella split-time delle stazioni.
3.  Gestione penalità e ricalcolo in tempo reale dei tempi della sessione.

---

## WP 6: Protocolli di Sincronizzazione Locale e Cloud

*   **Riferimento WBS:** Epic 3 (Sottosistema Sincronizzazione Dati)
*   **User Stories Associate:** US-S-01 (Sync Bluetooth Watch->Phone) [5 SP], US-S-02 (Sync Phone->Cloud) [5 SP], US-S-03 (Push Cloud->Watch) [8 SP]
*   **Responsabile del WP:** Sara Viola (Mobile Integration Specialist)
*   **Risorse Assegnate:** Sara Viola (Mobile Integration Specialist), Luca Rossi (Senior Wearable Developer), Giovanni Manca (Tech Lead)
*   **Sforzo Stimato:** 18 Story Points

### Obiettivo e Attività Principali
Sviluppare i protocolli di comunicazione tra Watch, Smartphone e Cloud. Le attività comprendono:
1.  Sincronizzazione Bluetooth per scaricare i dati dall'orologio al telefono in assenza di rete.
2.  Sviluppo client HTTP per upload asincrono su Cloud (JSON).
3.  Integrazione notifiche Push (APNs) per inviare i workout programmati dall'app all'orologio.

---



### Approvazione Formale del Documento
*   **Approvato da (Product Owner):** *Chiara Bertocchi* (Firma digitale registrata il 14 Feb 2026)  
*   **Approvato da (Scrum Master):** *Andrea Zavatta* (Firma digitale registrata il 14 Feb 2026)
