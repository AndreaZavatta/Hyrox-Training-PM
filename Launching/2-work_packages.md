# Schede di Dettaglio dei Work Packages (WP) - Copertura Completa WBS

Questo documento organizza l'intero Product Backlog (128 SP) in **6 Work Packages (WP) strutturati**, garantendo la scomposizione e la copertura al 100% di tutte le Epiche e User Story definite nella WBS.

> [!NOTE]
> **Giustificazione dell'Approccio Globale:**
> I Work Packages sono tipicamente utilizzati in modo selettivo per i task sul percorso critico, ad alto rischio o complessi. Adottando Scrum puro, abbiamo scelto di mappare l'**intero backlog** in 6 macro Work Packages (coincidenti con le Epiche del nostro Product Backlog) come strumento di controllo amministrativo di alto livello e tracciabilità verso gli stakeholder esterni, fermo restando che l'esecuzione avviene interamente tramite sprint backlog ed eventi Scrum. Il focus dello Scrum Master e del Tech Lead nella compilazione e nel monitoraggio delle schede si concentra primariamente sui WP critici:
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

### Descrizione dell'Obiettivo
Pianificare e realizzare l'architettura dei dati (schema del database) e l'infrastruttura di integrazione continua (CI/CD) per abilitare lo sviluppo parallelo sui sottosistemi WatchOS, Web Frontend e Cloud Backend.

### Deliverable in Input
1.  Specifiche architetturali e requisiti tecnologici (iOS, watchOS, Cloud Node.js/PostgreSQL).
2.  Definizione dei flussi dati generali e del ciclo di vita del workout.

### Attività di Dettaglio
1.  Inizializzazione dei repository Git e configurazione dei branch protetti (`main`, `review`, `develop`).
2.  Configurazione delle pipeline CI/CD (GitHub Actions) per l'esecuzione automatica di linter, test unitari e build watchOS/Web.
3.  Progettazione dello schema ER (Entity-Relationship) del database relazionale.
4.  Scrittura delle specifiche OpenAPI/Swagger per i contratti delle API.

### Deliverable in Output
1.  Repository attivi con build automatizzate funzionanti.
2.  Schema ER del database validato e script di migrazione SQL iniziali.
3.  Swagger/OpenAPI UI esposta sugli ambienti di sviluppo.

---

## WP 2: Sviluppo App Wearable (Interfaccia, Caching Locale & Fallback)

*   **Riferimento WBS:** Epic 1 (Sottosistema Smartwatch) - Feature 1.1, 1.3 (in parte), 1.4
*   **User Stories Associate:** US-W-01 (UI Base) [5 SP], US-W-02 (Note Coach) [3 SP], US-W-03 (Fallback Manuale) [5 SP], US-W-05 (Caching Locale) [8 SP], US-W-06 (Report Locale) [3 SP]
*   **Responsabile del WP:** Luca Rossi (Senior Wearable Developer)
*   **Risorse Assegnate:** Luca Rossi (Senior Wearable Developer), Sara Viola (Mobile Developer / QA)
*   **Sforzo Stimato:** 24 Story Points

### Descrizione dell'Obiettivo
Realizzare l'applicazione nativa per Apple Watch focalizzandosi sulla leggibilità sotto stress fisico (UI ad alto contrasto), la memorizzazione locale dei dati in assenza di segnale e la transizione manuale di backup.

### Deliverable in Input
1.  Mockup grafici ad alto contrasto per schermi OLED Apple Watch.
2.  Linee guida di usabilità in contesti ad alta intensità cardiaca.

### Attività di Dettaglio
1.  Sviluppo dell'interfaccia utente nativa watchOS in SwiftUI (caratteri grandi, colori saturi ad alto contrasto).
2.  Integrazione delle notifiche aptiche (vibrazioni del watch) per segnalare il passaggio di stazione.
3.  Implementazione del database locale SQLite (attraverso CoreData) per il caching offline dei dati inerziali e dei battiti cardiaci.
4.  Sviluppo del modulo di Fallback Manuale (avanzamento stazione tramite pressione simultanea dei tasti fisici dell'orologio).
5.  Creazione della schermata di riassunto post-allenamento sul watch.

### Deliverable in Output
1.  Applicazione watchOS (file `.app` compilabile) installabile sui dispositivi di test.
2.  Modulo CoreData per la persistenza offline validato con test di spegnimento improvviso.

---

## WP 3: Algoritmo di Riconoscimento Automatico & Flessibilità Gara

*   **Riferimento WBS:** Epic 1 (Sottosistema Smartwatch) - Feature 1.2, 1.3 (in parte)
*   **User Stories Associate:** US-TEC-03 (Spike Acquisizione Sensori) [5 SP], US-W-04 (Modello Core Algoritmo) [13 SP], US-W-07 (Skip & Riordina Stazioni) [13 SP]
*   **Responsabile del WP:** Giovanni Manca (Tech Lead & ML Specialist)
*   **Risorse Assegnate:** Giovanni Manca (Tech Lead & ML Specialist), Luca Rossi (Senior Wearable Developer), Sara Viola (Mobile Developer)
*   **Sforzo Stimato:** 31 Story Points

### Descrizione dell'Obiettivo
Sviluppare il classificatore matematico per il cambio automatico delle stazioni e le transizioni (Roxzone) sulla base della pianificazione inserita dal coach, integrando la flessibilità di riordino degli esercizi qualora i macchinari nel box siano occupati.

### Deliverable in Input
1.  Tracciati inerziali grezzi registrati a 50Hz durante lo Spike dello Sprint 4.
2.  Dinamiche fisiche standard delle stazioni Hyrox (es. oscillazione burpees vs trazione rowing).

### Attività di Dettaglio
1.  **Raccolta dati (Spike):** Registrazione di sessioni reali su 10 atleti.
2.  **Addestramento modello:** Sviluppo del classificatore basato su CoreMotion per isolare le signatures di movimento.
3.  **Integrazione logica di Skip/Riordino:** Sviluppo dell'algoritmo di deviazione per permettere all'atleta di riordinare le stazioni dal watch senza interrompere la telemetria globale.

### Deliverable in Output
1.  Modulo Swift `HyroxClassifier` integrato nell'app.
2.  Algoritmo di riallineamento dati per stazioni non sequenziali.
3.  Report di accuratezza nei test di laboratorio (baseline target $\ge$ 90%).

---

## WP 4: Web Dashboard (Profilazione, Sicurezza & Workout Builder)

*   **Riferimento WBS:** Epic 2 (Sottosistema Dashboard) - Feature 2.1, 2.2, 2.4
*   **User Stories Associate:** US-D-01 (Auth & ACL) [5 SP], US-D-02 (Profilazione Fisiologica) [3 SP], US-D-06 (Builder Workout) [8 SP], US-D-07 (Dashboard Offline) [8 SP]
*   **Responsabile del WP:** Elena Bianchi (Senior Frontend Developer)
*   **Risorse Assegnate:** Elena Bianchi (Senior Frontend Developer), Matteo Neri (Backend Developer)
*   **Sforzo Stimato:** 24 Story Points

### Descrizione dell'Obiettivo
Sviluppare l'infrastruttura web della Dashboard, comprendente l'autenticazione a ruoli (Coach/Atleta), la scheda fisiologica e lo strumento visivo per la pianificazione degli allenamenti (Workout Builder).

### Deliverable in Input
1.  Modello dei dati delle entità *Utente*, *Workout* e *Template*.
2.  Regole e limiti del Rulebook ufficiale Hyrox per sesso e categoria (Open/Pro).

### Attività di Dettaglio
1.  Sviluppo del portale React con autenticazione JWT e controllo accessi (ACL).
2.  Implementazione del Workout Builder visivo per configurare sequenze, carichi, volumi e tempistiche.
3.  **Pre-inserimento dati:** Sviluppo della logica per cui il builder propone automaticamente i pesi ufficiali conformi al rulebook della categoria dell'atleta selezionato.
4.  Configurazione del Service Worker per il caching delle risorse web (Dashboard Offline).

### Deliverable in Output
1.  Portale web per la gestione dei profili e dei template dei workout.
2.  Pagine web con supporto PWA (Progressive Web App) per il caricamento offline.

---

## WP 5: Modulo Analytics (Grafici di Pacing, Tabella Comparativa & Sanzioni)

*   **Riferimento WBS:** Epic 2 (Sottosistema Dashboard) - Feature 2.3
*   **User Stories Associate:** US-D-03 (Visualizzazione Comparativa Team) [8 SP], US-D-04 (Motore Grafici di Pacing Overlay) [8 SP], US-D-05 (Gestione Sanzioni/Penalità) [5 SP]
*   **Responsabile del WP:** Elena Bianchi (Senior Frontend Developer)
*   **Risorse Assegnate:** Elena Bianchi (Senior Frontend Developer), Matteo Neri (Backend Developer / Data Analyst)
*   **Sforzo Stimato:** 21 Story Points

### Descrizione dell'Obiettivo
Progettare e implementare il motore analitico della dashboard che consente al coach di visualizzare i dati del team, sovrapporre i grafici di pacing degli atleti rispetto ai target teorici ed effettuare debriefing storici integrando sanzioni e no-rep.

### Deliverable in Input
1.  Dataset di telemetria completati (tempi di split delle 8 stazioni, Roxzone, FC e ritmi di pacing).
2.  Mockup grafici dei diagrammi a linee sovrapposti per l'analisi comparativa.

### Attività di Dettaglio
1.  **Generazione Grafici di Pacing Overlay:** Sviluppo del componente grafico interattivo (usando librerie come Recharts o Chart.js) che sovrappone le curve di andatura reale di più atleti (fino a 4) rispetto alla linea di pacing teorica stabilita dal coach nel builder.
2.  **Tabella Comparativa Team:** Creazione dell'interfaccia a colonne per confrontare istantaneamente gli split-time delle stazioni dei 4 atleti, evidenziando in rosso le deviazioni negative e in verde i record.
3.  **Gestione Sanzioni e Penalità:** Sviluppo del modulo per inserire sanzioni di tempo (es. +30 secondi per mancata esecuzione o no-rep) con ricalcolo in tempo reale dei tempi di split e del totale della sessione.

### Deliverable in Output
1.  Modulo Dashboard `TeamAnalytics` integrato con grafici interattivi di pacing.
2.  Endpoint API per il calcolo e la presenza delle sanzioni (`POST /api/workouts/{id}/penalties`).
3.  Funzione di esportazione PDF del report comparativo per il debriefing del team.

---

## WP 6: Protocolli di Sincronizzazione Locale e Cloud

*   **Riferimento WBS:** Epic 3 (Sottosistema Sincronizzazione Dati)
*   **User Stories Associate:** US-S-01 (Sync Bluetooth Watch->Phone) [5 SP], US-S-02 (Sync Phone->Cloud) [5 SP], US-S-03 (Push Cloud->Watch) [8 SP]
*   **Responsabile del WP:** Sara Viola (Mobile Integration Specialist)
*   **Risorse Assegnate:** Sara Viola (Mobile Integration Specialist), Luca Rossi (Senior Wearable Developer), Giovanni Manca (Tech Lead)
*   **Sforzo Stimato:** 18 Story Points

### Descrizione dell'Obiettivo
Sviluppare il protocollo di comunicazione a due stadi che consenta il trasferimento del workout dal Cloud al Watch e l'invio della telemetria finale dal Watch alla Dashboard.

### Deliverable in Input
1.  Specifiche del framework CoreBluetooth di Apple.
2.  Credenziali e certificati APNs (Apple Push Notification service).

### Attività di Dettaglio
1.  Implementazione del trasferimento locale CoreBluetooth per scaricare i dati telemetrici dall'Apple Watch allo smartphone accoppiato (senza necessità di internet).
2.  Sviluppo del client HTTP su smartphone per l'upload in background (appena disponibile la rete cellular/Wi-Fi) del file JSON al server Cloud.
3.  Integrazione del server APNs per l'invio in push silente del workout pre-schedulato dal coach direttamente sul watch dell'atleta.

### Deliverable in Output
1.  Modulo `BluetoothSyncService` e `CloudSyncManager` integrati nelle app iOS/watchOS.
2.  Infrastruttura di notifica push configurata e testata con tempi di ricezione inferiori a 10 secondi.

---

## Appendice: Modelli Standard (Blank Forms) ad uso del PM Audit

Di seguito vengono riportati i template formali vuoti da utilizzare per la creazione di nuovi Work Packages o per l'assegnazione dei task.

### 1. Work Package Description Form (Template)

| **Dati Generali** | | | |
| :--- | :--- | :--- | :--- |
| **WP ID:** `[WP-XXX]` | **WBS Ref (Epic/Feature):** `[Epic X.X]` | **Codice Conto Budget:** `[Budget-Cod]` | **Data Stesura:** `[GG/MM/AAAA]` |
| **Nome WP:** | `[Nome del Work Package]` | | |
| **Responsabile (WP Manager):** | `[Nome Risorsa]` | **Ruolo:** | `[Tech Lead / Dev / QA]` |
| **Pianificazione** | | | |
| **Data Inizio Stimata:** | `[GG/MM/AAAA]` | **Data Fine Stimata:** | `[GG/MM/AAAA]` |
| **Sforzo Stimato (SP o Ore):** | `[X Story Points / Y Ore]` | **Costo Stimato (€):** | `[€ X.XXX]` |
| **Descrizione e Contenuto** | | | |
| **Descrizione dell'Obiettivo:** | *[Fornire una descrizione di alto livello dell'obiettivo del Work Package]* | | |
| **Deliverable in Input:** | 1. `[Elenco documenti/codice/requisiti necessari per iniziare]` <br>2. `[Specifiche UI/API di riferimento]` | | |
| **Attività di Dettaglio:** | 1. `[Task di dettaglio 1]` <br>2. `[Task di dettaglio 2]` <br>3. `[Task di dettaglio 3]` | | |
| **Deliverable in Output:** | 1. `[Codice compilabile/Repository attivo/Modulo di test]` <br>2. `[Documentazione/Schema di database/Report di test]` | | |
| **Criteri di Accettazione & Quality:** | 1. `[Criterio 1: es. Superamento test di regressione/Copertura test >= 80%]` <br>2. `[Criterio 2: es. Approvazione Code Review / Demo funzionante]` | | |
| **Approvazioni Formali** | | | |
| **Firma WP Manager:** | *`[Firma digitale o sigla]`* | **Data Approvazione:** | `[GG/MM/AAAA]` |
| **Firma Project Manager:** | *`[Firma digitale o sigla]`* | **Data Approvazione:** | `[GG/MM/AAAA]` |

---

### 2. Work Package Assignment Sheet (Template)

**Riferimento Work Package:** `[WP-XXX - Nome Work Package]`  
**Data di Emissione:** `[GG/MM/AAAA]`  

| ID Task | Descrizione Attività | Risorsa Assegnata | Sforzo Stimato (Ore/SP) | Data Inizio | Data Fine | Stato (Da Iniziare / In Corso / Done) | Firma di Accettazione Risorsa |
| :--- | :--- | :--- | :---: | :---: | :---: | :---: | :---: |
| **T-01** | `[Descrizione sintetica del task]` | `[Nome Risorsa]` | `[Xh / Y SP]` | `[GG/MM]` | `[GG/MM]` | `[Stato]` | `[Firma]` |
| **T-02** | `[Descrizione sintetica del task]` | `[Nome Risorsa]` | `[Xh / Y SP]` | `[GG/MM]` | `[GG/MM]` | `[Stato]` | `[Firma]` |
| **T-03** | `[Descrizione sintetica del task]` | `[Nome Risorsa]` | `[Xh / Y SP]` | `[GG/MM]` | `[GG/MM]` | `[Stato]` | `[Firma]` |
| **T-04** | `[Descrizione sintetica del task]` | `[Nome Risorsa]` | `[Xh / Y SP]` | `[GG/MM]` | `[GG/MM]` | `[Stato]` | `[Firma]` |

*Note di Coordinamento:* Le ore/SP effettive verranno rendicontate settimanalmente sulla board Jira del progetto. Eventuali scostamenti superiori al 15% rispetto allo sforzo stimato devono essere tempestivamente segnalati al WP Manager e al PM.

---

### Approvazione Formale del Documento
*   **Approvato da (Product Owner):** *Chiara Bertocchi* (Firma digitale registrata il 14 Feb 2026)  
*   **Approvato da (Scrum Master):** *Andrea Zavatta* (Firma digitale registrata il 14 Feb 2026)
