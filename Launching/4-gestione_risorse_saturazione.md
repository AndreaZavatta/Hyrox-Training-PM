# Gestione delle Risorse, Saturazione e Livellamento

Il presente documento definisce la strategia di gestione delle risorse umane del progetto "Hyrox Team Performance Optimizer". Vengono qui esplicitati il modello di Staffing, il bilanciamento del team secondo gli stili di apprendimento di Kolb, la programmazione della saturazione giornaliera (Resource Loading) e le tecniche di livellamento (Resource-Leveling).

---

## 1. Modello di Staffing e Classificazione del Team

Per garantire una chiara distinzione dei ruoli operativi, contrattuali e decisionali, i membri del progetto sono classificati come segue:

| Categoria | Nominativi | Ruolo e Responsabilità nel Progetto |
| :--- | :--- | :--- |
| **Co-Project Manager (Developer)** | **Andrea Zavatta** | Scrum Master / PM. Gestisce la schedula, il budget, la facilitazione Scrum e i rischi. |
| **Co-Project Manager (Client)** | **Chiara Bertocchi** | Product Owner (PO). Proprietaria del box Hyrox partner, definisce i requisiti di business e valida i rilasci. |
| **Core Team** | **Giovanni Manca**<br>**Luca Rossi**<br>**Elena Bianchi** | Sviluppatori chiave stabili sul progetto fin dalla fase di Planning. Giovanni cura l'architettura e l'algoritmo (ML); Luca si occupa di watchOS; Elena cura la Web Dashboard. |
| **Developer Team** | **Matteo Neri**<br>**Sara Viola** | Sviluppatori inseriti nella fase di Launching per supportare lo sviluppo verticale (Matteo per il database e il cloud backend; Sara per la sincronizzazione bluetooth e il controllo di qualità). |
| **Client Team** | **15 Coach Esterni**<br>**30 Atleti di Test** | Utenti finali e tester qualificati. Forniscono i feedback nelle Sprint Review e validano le build su TestFlight. |
| **Contracted Team** | *Nessuna risorsa esterna contrattualizzata* | Non si rende necessario il ricorso a consulenti o team esterni in quanto le competenze dello Scrum Team interno coprono l'intero fabbisogno del progetto. |

---

## 2. Bilanciamento del Team e Competenze (Cross-Functionality)

Il bilanciamento del team è un fattore critico di successo. Le competenze dei membri dello Scrum Team sono state assortite per garantire la massima copertura tecnica e operativa senza dipendenze esterne:

*   **Giovanni Manca (Tech Lead & ML):** Guida il team verso le scelte tecnologiche (Machine Learning e architettura).
*   **Luca Rossi (Wearable Developer):** Risorsa focalizzata sull'implementazione watchOS e integrazione hardware.
*   **Elena Bianchi (Frontend & UI/UX):** Fondamentale nella progettazione della dashboard e nell'esperienza utente.
*   **Matteo Neri & Sara Viola:** Sviluppatori focalizzati rispettivamente su backend/cloud e connettività Bluetooth/QA.
*   **Andrea Zavatta (SM/PM):** Bilancia la gestione del progetto e la rimozione dei blocchi operativi del team.

Questo assetto garantisce che il team sia auto-organizzato e *cross-funzionale*, come richiesto dalla metodologia.

---

## 3. Tabella di Saturazione delle Risorse (Resource Loading Chart)

Al fine di garantire l'assenza di **over-allocation** (sovrallocazione) e rispettare il vincolo delle 8 ore giornaliere lavorative (pari a 40 ore/settimana per risorsa), viene definita la schedula di dettaglio delle attività giornaliere per ciascuno sviluppatore.

Per evitare la tipica trappola del PM tradizionale (pianificare le risorse al 100% del tempo su compiti di puro sviluppo, ignorando il tempo perso in riunioni e allineamenti), la schedula adotta un **Focus Factor del 75%** (6 ore/giorno dedicate ad attività della WBS). Le restanti **2 ore/giorno (25%)** sono riservate all'Overhead organizzativo e alle cerimonie Scrum (Daily Scrum, Sprint Review, Planning, code review e compilazione del workbook).

Di seguito viene riportato, a titolo di esempio, il grafico di saturazione per lo **Sprint 4 (Sprint critico contenente lo Spike tecnologico sui sensori dell'Apple Watch)**:

### Schedula di Carico Giornaliero (Ore/Giorno) - Sprint 4 (G1 - G10)

| Risorsa / Ruolo | Task Assegnato (Riferimento WBS) | G1 | G2 | G3 | G4 | G5 | G6 | G7 | G8 | G9 | G10 | Stato / Carico |
| :--- | :--- | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| **Giovanni Manca**<br>(Tech Lead) | **TS-01**: Spike Sensori (WP3)<br>**TS-02**: API & DB Schema (WP1)<br>**Overhead / Cerimonie** | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | 3h<br>3h<br>2h | **Satura (FF 75%)**<br>(8h/giorno) |
| **Luca Rossi**<br>(Senior Wearable) | **TS-03**: UI watchOS Base (WP2)<br>**TS-04**: Supporto Spike (WP3)<br>**Overhead / Cerimonie** | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | 4h<br>2h<br>2h | **Satura (FF 75%)**<br>(8h/giorno) |
| **Elena Bianchi**<br>(Senior Frontend) | **TS-05**: UI Dashboard React (WP4)<br>**TS-06**: Stesura Doc UI (WP4)<br>**Overhead / Cerimonie** | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | 5h<br>1h<br>2h | **Satura (FF 75%)**<br>(8h/giorno) |
| **Matteo Neri**<br>(Backend Developer) | **TS-07**: Endpoint REST Auth (WP4)<br>**Overhead / Cerimonie** | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | **Satura (FF 75%)**<br>(8h/giorno) |
| **Sara Viola**<br>(Mobile Specialist) | **TS-08**: CoreBluetooth & Sync (WP6)<br>**Overhead / Cerimonie** | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | 6h<br>2h | **Satura (FF 75%)**<br>(8h/giorno) |

> [!IMPORTANT]
> **Gestione Realistica della Saturazione:**
> Ciascuna risorsa è pianificata esattamente per **80 ore complessive nello Sprint** (8 ore al giorno per 10 giorni lavorativi), suddivise in **60 ore su task WBS** e **20 ore su overhead organizzativo**. Questa ripartizione garantisce che le attività di coordinamento descritte nei *Working Agreements* (come i 15 minuti giornalieri di standup e le code review) siano coperte formalmente senza sottrarre tempo prezioso allo sviluppo attivo delle funzionalità, eliminando il rischio di over-allocation invisibile.

---

## 4. Strategie di Livellamento delle Risorse in Ambito Scrum (Resource-Leveling)

> [!NOTE]
> **Nota Metodologica sull'Approccio Agile:**
> In conformità con la metodologia ibrida del progetto, le classiche tecniche predittive di *Resource-Leveling* e i concetti di *Critical Path* e *Slack* vengono qui reinterpretati e mappati sui meccanismi di auto-organizzazione e pianificazione dello Sprint Backlog (componente Agile), evitando la rigida schedulazione waterfall per l'esecuzione iterativa.

Nel caso in cui si verifichino imprevisti, impedimenti o colli di bottiglia che mettono a rischio il completamento degli incrementi durante lo Sprint (ad esempio, complessità impreviste nell'elaborazione del filtro di Kalman durante lo Spike sui sensori), lo Scrum Team applica le seguenti strategie di livellamento auto-organizzato:

1.  **Gestione dei Task non Critici per lo Sprint Goal (Slack / Scorrimento Agile):**
    I task non posizionati sul percorso critico per il raggiungimento dello *Sprint Goal* (come la stesura della documentazione UI `TS-06` o l'ottimizzazione secondaria delle API) hanno margini di flessibilità. Gli sviluppatori possono sospendere temporaneamente o posticipare queste attività all'interno dello Sprint per concentrare l'effort sui task bloccanti, sfruttando il buffer di capacità.
2.  **Rimodulazione e Swarming sui Task Critici (Adjusting Task Duration / Focus):**
    Se un task fondamentale per lo Sprint Goal richiede più tempo del previsto, la sua durata viene estesa riducendo l'intensità lavorativa giornaliera dedicata ad altre storie dello Sprint. Il team applica lo *Swarming* (collaborazione simultanea di più sviluppatori sullo stesso elemento del backlog) per assicurarne il completamento entro la fine dello Sprint.
3.  **Supporto Interfunzionale e Sostituzione delle Risorse (Cross-Functional Collaboration):**
    Grazie alle competenze trasversali (T-shaped skills) dello Scrum Team, le risorse che completano in anticipo i propri task (es. Sara Viola che termina la configurazione bluetooth) supportano attivamente i colleghi impegnati sulle storie critiche (es. Luca Rossi per il debug della cache locale), fungendo da risorsa sostitutiva temporanea senza richiedere un intervento gerarchico esterno.
4.  **Straordinario Controllato come Extrema Ratio (Overtime):**
    Considerato esclusivamente come ultima risorsa per non compromettere l'obiettivo dello Sprint, l'uso dello straordinario è limitato a un massimo del **10% della capacità totale dello Sprint** (pari a 8 ore aggiuntive per sviluppatore per Sprint) e deve essere concordato internamente al team per far fronte a impedimenti bloccanti non risolvibili altrimenti.

---

*Documento redatto e finalizzato in sede di Kick-off dal Project Manager Andrea Zavatta.*
