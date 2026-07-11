# Product Backlog

Il Product Backlog completo e aggiornato in tempo reale (con epiche, sprint e tracciamento) è gestito interamente su **Jira** per mantenere una vera *Single Source of Truth* ed evitare ridondanze documentali:

*   **[🏃 Apri la Board Jira: Product Backlog](https://hyrox-training.atlassian.net/jira/software/projects/HTPO/boards/1/backlog)**

---

## Estratto Core User Stories (MVP)

Di seguito un estratto delle **4 User Story più critiche** (dal punto di vista del rischio o del business value) per dimostrare il formato metodologico adottato (struttura Agile, criteri di accettazione testabili e stime in Story Points).

### **US-W-04: Algoritmo di Riconoscimento Cambio Stazione via Sensori** (Valore di Business Core)
*   **Rif. WBS/RBS:** WBS 1.2 / RBS 1.1.2.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta in gara,
    *   *voglio* che lo smartwatch riconosca autonomamente l'inizio e la fine delle 8 stazioni funzionali Hyrox e delle Roxzone di corsa tramite i sensori inerziali,
    *   *affinché* non debba effettuare alcuna interazione fisica con lo schermo del watch durante l'intera performance.
*   **Criteri di Accettazione:**
    *   L'algoritmo deve discriminare la transizione tra le 8 stazioni e la corsa sfruttando la sequenza programmata del workout pre-schedulato per restringere lo spazio degli stati.
    *   L'accuratezza del riconoscimento automatico deve attestarsi a una soglia ≥ 90% in ambiente controllato prima del rilascio (Lab Testing).
*   **Stima:** `13 Story Points` (Alta complessità / Rischio tecnologico. Richiede US-TEC-03 come prerequisito).

### **US-W-03: Transizione Manuale Gestita (Fallback Trigger)** (Mitigazione Rischio)
*   **Rif. WBS/RBS:** WBS 1.3 / RBS 1.1.0.3 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta sotto sforzo estremo in gara o allenamento,
    *   *voglio* poter attivare manualmente il passaggio alla stazione successiva tramite la pressione coordinata dei tasti fisici del watch,
    *   *affinché* possa disporre di un meccanismo di fallback affidabile qualora l'algoritmo automatico fallisca o introduca ritardi.
*   **Criteri di Accettazione:**
    *   La transizione manuale si attiva tramite pressione contemporanea della Digital Crown e del tasto laterale per 1.0 secondi.
    *   L'attivazione genera un Feedback aptico (vibrazione) per dare conferma fisica immediata all'atleta senza obbligarlo a guardare lo schermo.
*   **Stima:** `5 Story Points` (Media complessità).

### **US-D-06: Builder Pianificazione Sessioni e Gestione Template** (Funzione Core Coach)
*   **Rif. WBS/RBS:** WBS 2.2 / RBS 2.2.1.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* configurare graficamente un allenamento combinando blocchi di corsa e stazioni funzionali e salvare la configurazione come template,
    *   *affinché* possa pianificare sessioni personalizzate per gli atleti riducendo i tempi di inserimento ripetitivo.
*   **Criteri di Accettazione:**
    *   Il builder deve permettere la creazione di un workout trascinando o selezionando blocchi di stazioni funzionali e corsa (Drag&Drop).
    *   Ogni blocco deve prevedere campi contestuali: Peso (kg), Distanza (metri), Ripetizioni e Note per l'atleta.
*   **Stima:** `8 Story Points` (Alta complessità interfaccia e gestione dati).

### **US-TEC-03: Spike Tecnologico - Fattibilità Algoritmo** (Abilitatore Tecnico)
*   **Rif. WBS:** WBS 1.2 (Priorità: **MUST**)
*   **Descrizione:** Spike tecnico per l'acquisizione di tracciati accelerometrici grezzi su atleti in palestra e validazione iniziale del classificatore per abbattere il rischio tecnologico di US-W-04.
*   **Criteri di Accettazione:**
    *   Almeno 10 sessioni di allenamento registrate con dati accelerometro/giroscopio grezzi.
    *   Algoritmo preliminare testato in locale (Python) con accuratezza minima del 70%.
    *   Documento di sintesi tecnica che definisce la fattibilità e i vincoli per l'implementazione sul watch.
*   **Stima:** `5 Story Points` (Time-boxed: massimo sforzo dedicato pari a 5 story points, indipendentemente dal risultato).

---
> **Nota metodologica:** Tutte le altre User Story (Sincronizzazione Bluetooth, Autenticazione, Report offline, ecc.) sono tracciate e regolarmente stimate all'interno di **Jira**.
