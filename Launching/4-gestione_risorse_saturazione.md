# Gestione delle Risorse, Saturazione e Livellamento

Il presente documento definisce la strategia di gestione delle risorse umane del progetto "Hyrox Team Performance Optimizer". In conformità con le linee guida della [teoria del corso](file:///home/zava/Projects/PM-project/Teoria/8%20-%20Launching%20Process%20Group%20-%20Ver.3.3.md), vengono qui esplicitati il modello di Staffing, il bilanciamento del team secondo gli stili di apprendimento di Kolb, la programmazione della saturazione giornaliera (Resource Loading) e le tecniche di livellamento (Resource-Leveling).

---

## 1. Modello di Staffing e Classificazione del Team

Per garantire una chiara distinzione dei ruoli operativi, contrattuali e decisionali, i membri del progetto sono classificati secondo la tassonomia metodologica di Wysocki:

| Categoria | Nominativi | Ruolo e Responsabilità nel Progetto |
| :--- | :--- | :--- |
| **Co-Project Manager (Developer)** | **Andrea Zavatta** | Scrum Master / PM. Gestisce la schedula, il budget, la facilitazione Scrum e i rischi. |
| **Co-Project Manager (Client)** | **Chiara Bertocchi** | Product Owner (PO). Proprietaria del box Hyrox partner, definisce i requisiti di business e valida i rilasci. |
| **Core Team** | **Giovanni Manca**<br>**Luca Rossi**<br>**Elena Bianchi** | Sviluppatori chiave stabili sul progetto fin dalla fase di Planning. Giovanni cura l'architettura e l'algoritmo (ML); Luca si occupa di watchOS; Elena cura la Web Dashboard. |
| **Developer Team** | **Matteo Neri**<br>**Sara Viola** | Sviluppatori inseriti nella fase di Launching per supportare lo sviluppo verticale (Matteo per il database e il cloud backend; Sara per la sincronizzazione bluetooth e il controllo di qualità). |
| **Client Team** | **15 Coach Esterni**<br>**30 Atleti di Test** | Utenti finali e tester qualificati. Forniscono i feedback nelle Sprint Review e validano le build su TestFlight. |
| **Contracted Team** | *Nessuna risorsa esterna contrattualizzata* | Non si rende necessario il ricorso a consulenti o team esterni in quanto le competenze dello Scrum Team interno coprono l'intero fabbisogno del progetto. |

---

## 2. Bilanciamento del Team (Modello dei Learning Styles di David Kolb)

Trovare il giusto bilanciamento nel team è un fattore critico di successo. Le competenze e le attitudini dei membri dello Scrum Team sono state bilanciate mappando i loro profili individuali sulle quattro dimensioni degli stili di apprendimento di David Kolb:

| | **Sperimentazione Attiva (AE)**<br>*(Doing / Azione)* | **Osservazione Riflessiva (RO)**<br>*(Watching / Osservazione)* |
| :--- | :--- | :--- |
| **Esperienza Concreta (CE)**<br>*(Feeling / Percezione)* | **ACCOMMODATING** (Orientato al Fare)<br>• **Sara Viola** (QA & Integration)<br>• **Andrea Zavatta** (SM/PM - parziale) | **DIVERGING** (Orientato alle Idee)<br>• **Elena Bianchi** (Frontend & UI/UX) |
| **Concettualizzazione Astratta (AC)**<br>*(Thinking / Pensiero)* | **CONVERGING** (Orientato all'Applicazione)<br>• **Luca Rossi** (Wearable Developer)<br>• **Giovanni Manca** (Tech Lead - parziale) | **ASSIMILATING** (Orientato ai Modelli)<br>• **Giovanni Manca** (Algorithm & ML)<br>• **Andrea Zavatta** (SM/PM - parziale) |
*Note descrittive dei profili:*
*   **Giovanni Manca (Assimilating / Converging):** Ha una forte propensione a raccogliere dati, progettare modelli teorici complessi (l'algoritmo matematico di activity recognition) e identificare la migliore soluzione tecnica tra diverse alternative. Guida il team verso scelte tecnologiche razionali.
*   **Luca Rossi (Converging):** Risorsa focalizzata sulla risoluzione di problemi complessi e sull'implementazione tecnica (watchOS SDK, caching locale offline). Preferisce l'azione logica e la programmazione sistematica al brainstorming esteso.
*   **Elena Bianchi (Diverging):** Mette in campo una spiccata creatività ed elasticità mentale. Riesce a visualizzare i problemi da molteplici prospettive, risultando fondamentale nella progettazione della UI/UX della dashboard e dei grafici di pacing overlay (Miro co-design).
*   **Sara Viola (Accommodating):** Estremamente orientata ai risultati sul campo e all'azione. Si adatta rapidamente ai cambiamenti ed eccelle nel testing di usabilità a contatto diretto con gli atleti e nell'integrazione di rete in ambienti instabili.
*   **Andrea Zavatta (Assimilating / Accommodating):** Bilancia la capacità di visione macroscopica del progetto (raccolta e modellazione dei dati di avanzamento) con un approccio pragmatico volto a facilitare la collaborazione e a rimuovere i blocchi operativi del team.

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

## 4. Strategie di Livellamento delle Risorse (Resource-Leveling)

Nel caso in cui si verifichino imprevisti, assenze o colli di bottiglia durante l'esecuzione dello Sprint (ad esempio, complessità impreviste nell'elaborazione del filtro di Kalman durante lo Spike sui sensori), lo Scrum Master applica le seguenti strategie di livellamento approvate:

1.  **Utilizzo degli Slack (Margini di Scorrimento):**
    I task non posizionati sul *Critical Path* (come la stesura della documentazione UI `TS-06` o l'ottimizzazione secondaria delle API) hanno dei margini di scorrimento. Lo Scrum Master può ritardarne l'inizio senza impattare la data di conclusione dello Sprint, liberando ore per supportare i task critici.
2.  **Rimodulazione della Durata dei Task (Lengthening Task Duration):**
    Se un task critico richiede più tempo, la sua durata viene estesa riducendone l'intensità lavorativa giornaliera (es. da 8 ore/giorno a 4 ore/giorno) e distribuendolo su più giorni dello Sprint, parallelizzando altre attività non critiche.
3.  **Sostituzione e Supporto delle Risorse (Resource Substitution):**
    Grazie alle competenze trasversali del team, le risorse scariche o in anticipo sui propri task (es. Sara Viola che termina in anticipo la configurazione bluetooth) possono essere riallocate in supporto alle risorse critiche (es. Luca Rossi per il debug della cache locale).
4.  **Straordinario Controllato (Overtime):**
    Considerato come ultima risorsa (*Last Resort*), l'utilizzo dello straordinario è limitato a un massimo del **10% della capacità totale dello Sprint** (pari a 8 ore aggiuntive per sviluppatore per Sprint) e deve essere autorizzato dal PM per coprire esclusivamente rilasci di milestone bloccanti.

---

*Documento redatto e finalizzato in sede di Kick-off dal Project Manager Andrea Zavatta.*
