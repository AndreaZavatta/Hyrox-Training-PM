# Product Backlog: Hyrox Team Performance Optimizer

Il Product Backlog è lo strumento dinamico che raccoglie tutti i requisiti, le funzionalità e i miglioramenti del sistema. In linea con i principi Scrum, le stime definitive in Story Points (scala di Fibonacci) sono di **competenza esclusiva del Team di Sviluppo** e verranno assegnate durante le sessioni periodiche di Backlog Refinement.

Ai fini della pianificazione della release e dell'allineamento con la baseline della WBS, in questa sede vengono presentate delle **Stime Preliminari di Baseline**. Per gli elementi di forte innovazione o R&D (come l'algoritmo di riconoscimento sensori), è pianificato uno *Spike Tecnologico* preliminare (US-TEC-03) per ridurre l'incertezza e consentire una stima più accurata dell'implementazione core (US-W-04).

---

## 1. Governance e Standard di Qualità

Per garantire la massima qualità e coerenza del flusso Scrum, il team adotta i seguenti pilastri metodologici:

### Definition of Ready (DoR)
Un elemento del Backlog (User Story o Technical Story) è considerato **Ready** (Pronto per essere inserito in uno Sprint) quando soddisfa i seguenti criteri:
1. **Formato Standard:** È descritto nel formato *"Come [Ruolo] voglio [Azione] affinché [Valore]"*.
2. **Criteri di Accettazione:** I criteri di accettazione sono definiti in modo chiaro, non ambiguo e testabile.
3. **Dipendenze Risolte:** Tutte le dipendenze esterne (es. asset grafici, specifiche API, autorizzazioni hardware) sono state identificate e risolte.
4. **Dimensionamento Corretto:** La User Story è sufficientemente piccola da poter essere completata entro i limiti di un singolo Sprint.
5. **Stima del Team:** Il team di sviluppo ha analizzato la storia ed espresso una stima in Story Points (non è più `TBD`).
6. **Comprensione Condivisa:** C'è stato un confronto diretto tra Product Owner e Team per chiarire ogni dubbio sul business value.

### Definition of Done (DoD)
Una User Story è considerata **Done** (Completata e incrementabile nel prodotto rilasciabile) solo quando soddisfa tutti i seguenti criteri:
1. **Codice Scritto e Standardizzato:** Il codice è completato, segue le linee guida di stile del progetto ed è privo di warning significativi.
2. **Peer Review:** Il codice è stato sottoposto a Code Review tramite Pull Request e approvato da almeno un altro membro del team (es. Tech Lead o Senior Dev).
3. **Unit & Integration Testing:** 
   - I test unitari sulle componenti core e le API sono stati scritti e superati con successo (target di copertura ≥ 80% della logica di business).
   - I test di integrazione per i flussi di sincronizzazione dati sono superati.
4. **Deploy in Staging:** La funzionalità è stata rilasciata nell'ambiente di Staging/Testing per la validazione.
5. **Verifica dei Criteri di Accettazione:** Tutti i criteri di accettazione definiti nella User Story sono stati verificati e superati tramite test manuali o automatici.
6. **Approvazione del Product Owner:** Il Product Owner ha visionato la funzionalità demo ed ha formalmente accettato la storia nel sistema di tracciamento.
7. **Nessun Bug Aperto:** Non vi sono anomalie note aperte (con priorità Major, Critical o Blocker) introdotte dal nuovo codice.

---

## 2. User Stories del Product Backlog

Di seguito sono elencate le User Stories strutturate, suddivise per i tre sottosistemi principali identificati nella WBS/RBS.

### 2.1 Sottosistema Smartwatch (Wearable) — *Rif. WBS 4.x / RBS Req. 1*

#### **US-W-01: Interfaccia Utente Base ad Alto Contrasto**
*   **Rif. WBS/RBS:** WBS 4.1 / RBS 1.1.6.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta sotto sforzo cardiaco e muscolare estremo durante un allenamento Hyrox,
    *   *voglio* un'interfaccia smartwatch ad alto contrasto con pulsanti di grandi dimensioni e scritte ben leggibili,
    *   *affinché* possa monitorare i dati essenziali di sessione (FC, tempo totale, split attivo) a colpo d'occhio senza distogliere il focus dal gesto atletico.
*   **Criteri di Accettazione:**
    *   La palette colori dell'interfaccia deve basarsi su sfondo nero puro (OLED-friendly) e testo in giallo.
    *   La dimensione dei caratteri per le metriche primarie deve essere di almeno 24pt.
    *   I pulsanti interattivi a schermo (es. pausa, transizione) devono coprire almeno il 30% della superficie utile del display per facilitare il tocco con dita bagnate o sudate.
    *   La UX deve essere validata tramite test di usabilità ottenendo un SUS Score ≥ 80/100.
*   **Stima:** `5 Story Points` (Media complessità; sviluppo e test del layout grafico nativo watchOS)

#### **US-W-02: Visualizzazione Note del Coach sulla Stazione Attiva**
*   **Rif. WBS/RBS:** WBS 4.2 / RBS 1.1.3.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta in allenamento,
    *   *voglio* visualizzare sul display dello smartwatch le note specifiche scritte dal coach per la stazione attiva (es. peso dello sled, target di watt sul row, note tecniche),
    *   *affinché* possa eseguire l'esercizio esattamente come pianificato senza dover interrompere l'allenamento per consultare il telefono o cartelli cartacei.
*   **Criteri di Accettazione:**
    *   Le note devono apparire in un'area testuale dedicata nella schermata dell'esercizio in corso.
    *   La lunghezza massima visualizzabile delle note è limitata a 100 caratteri per evitare scrolling complessi.
    *   Se il workout non contiene note per la stazione attiva, la sezione viene nascosta ridistribuendo lo spazio per le metriche fisiche.
*   **Stima:** `3 Story Points` (Bassa complessità; ricezione dati e visualizzazione stringa dinamica)

#### **US-W-03: Transizione Manuale Gestita (Fallback Trigger)**
*   **Rif. WBS/RBS:** WBS 4.3 / RBS 1.1.0.3 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta sotto sforzo estremo in gara o allenamento,
    *   *voglio* poter attivare manualmente il passaggio alla stazione successiva tramite una gesture semplice o la pressione coordinata dei tasti fisici del watch,
    *   *affinché* possa disporre di un meccanismo di fallback affidabile e immediato qualora l'algoritmo automatico fallisca o introduca ritardi nel rilevamento della transizione.
*   **Criteri di Accettazione:**
    *   La transizione manuale si attiva tramite pressione contemporanea della Digital Crown e del tasto laterale per 1.0 secondi (per prevenire attivazioni accidentali).
    *   L'attivazione genera una vibrazione aptica forte (Haptic Feedback) per dare conferma fisica immediata all'atleta senza obbligarlo a guardare lo schermo.
    *   Deve essere disponibile un comando "Undo/Annulla" visibile a schermo per 3 secondi dopo la transizione, per ripristinare lo stato precedente in caso di errore.
*   **Stima:** `5 Story Points` (Media complessità; cattura input pulsanti fisici, feedback aptico e gestione timer/stato di Undo)

#### **US-W-04: Algoritmo di Riconoscimento Cambio Stazione via Sensori**
*   **Rif. WBS/RBS:** WBS 4.4 / RBS 1.1.2.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta in gara,
    *   *voglio* che lo smartwatch riconosca autonomamente l'inizio e la fine delle 8 stazioni funzionali Hyrox e delle Roxzone di corsa tramite i sensori inerziali (accelerometro e giroscopio),
    *   *affinché* non debba effettuare alcuna interazione fisica con lo schermo del watch durante l'intera performance.
*   **Criteri di Accettazione:**
    *   L'algoritmo deve discriminare la transizione delle 8 stazioni Hyrox standard (SkiErg, Sled Push, Sled Pull, Burpee Broad Jumps, Rowing, Farmers Carry, Sandbag Lunges, Wall Balls) rispetto alla corsa (Roxzone).
    *   L'algoritmo deve sfruttare la sequenza programmata del workout pre-schedulato per restringere lo spazio degli stati e aumentare l'accuratezza.
    *   L'accuratezza del riconoscimento automatico deve attestarsi a una soglia ≥ 90% in ambiente controllato prima del rilascio (Lab Testing).
*   **Stima:** `13 Story Points` (Alta complessità / Rischio tecnologico. Questa è una stima preliminare di baseline ad alto rischio; lo Spike tecnologico programmato in US-TEC-03 ridurrà le incognite prima della stima definitiva nel Refinement di Sprint)

#### **US-W-05: Caching Locale Continuo (Offline-First)**
*   **Rif. WBS/RBS:** WBS 4.5 / RBS 1.1.5.1 (Priorità: **SHOULD**)
*   **User Story:**
    *   *Come* atleta,
    *   *voglio* che tutti i dati della mia sessione (frequenza cardiaca, split times, accelerazioni) siano salvati continuamente in un database locale sullo smartwatch,
    *   *affinché* non mi debba portare dientro il cellulare per tenerlo collegato tramite bluetooth al cellulare.
*   **Criteri di Accettazione:**
    *   I dati grezzi e processati devono essere scritti su storage locale persistente (CoreData/SQLite) a intervalli regolari (massimo 5 secondi).
    *   In caso di riavvio forzato del dispositivo, l'app all'avvio deve ripristinare lo stato dell'allenamento interrotto recuperando i dati dalla cache locale.
    *   La cache locale deve poter contenere dati di sessione fino a un maximum di 5 ore continue ad alta risoluzione.
*   **Stima:** `8 Story Points` (Alta complessità; integrazione CoreData/SQLite per persistenza continuativa ad alta frequenza e prevenzione del memory leak)

#### **US-W-06: Report Locale di Fine Sessione**
*   **Rif. WBS/RBS:** WBS 4.6 / RBS 1.1.4.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta,
    *   *voglio* visualizzare un riepilogo sintetico dei miei risultati sul watch immediatamente dopo la conclusione della sessione,
    *   *affinché* possa conoscere all'istante i miei split times, i tempi di transizione e l'andamento medio delle varie stazioni senza dover prendere lo smartphone.
*   **Criteri di Accettazione:**
    *   La schermata di riepilogo finale deve mostrare: Tempo Totale, Tabella degli Split delle 8 stazioni, Tempo complessivo speso in Roxzone e FC Media di sessione.
    *   L'interfaccia deve consentire lo scorrimento verticale rapido e mostrare un indicatore visivo se la sessione non è ancora sincronizzata con lo smartphone.
*   **Stima:** `3 Story Points` (Bassa complessità; calcolo metriche locali a fine sessione e rendering grafico della tabella split)

#### **US-W-07: Flessibilità dell'Allenamento (Skip & Riordina Stazioni)**
*   **Rif. WBS/RBS:** WBS 4.2 / RBS 1.1.1.1 - 1.1.1.2 (Priorità: **COULD**)
*   **User Story:**
    *   *Come* atleta in allenamento in una palestra affollata,
    *   *voglio* poter saltare (skip) la stazione corrente o modificare l'ordine dei blocchi di lavoro direttamente dall'orologio,
    *   *affinché* possa proseguire la sessione adattandomi alla disponibilità immediata degli attrezzi senza alterare la correttezza del tracciamento.
*   **Criteri di Accettazione:**
    *   L'interfaccia dell'orologio deve presentare una gesture o un tasto secondario per accedere alla lista dei blocchi ed effettuare lo "Skip" o il "Riordina".
    *   L'azione di deviazione deve contrassegnare i dati esportati con un flag specifico ("Esercizio Saltato / Riordinato") per informare correttamente il coach.
*   **Stima:** `8 Story Points` (Alta complessità; gestione della macchina a stati dell'orologio in caso di variazione della sequenza pianificata)

---

### 2.2 Sottosistema Dashboard (Web/Smartphone) — *Rif. WBS 5.x / RBS Req. 2*

#### **US-D-01: Autenticazione Sicura e Controllo Accessi (ACL)**
*   **Rif. WBS/RBS:** WBS 5.1 / RBS 2.3.1.1 - 2.3.1.2 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* utente del sistema (coach o atleta),
    *   *voglio* potermi registrare ed accedere in sicurezza alla piattaforma web tramite credenziali personali,
    *   *affinché* le mie informazioni e i dati sulle prestazioni del team siano protetti e visibili solo a soggetti autorizzati.
*   **Criteri di Accettazione:**
    *   L'accesso deve prevedere due ruoli distinti: Coach (creazione workout, modifica sanzioni, analisi completa team) e Atleta (visualizzazione in sola lettura dei propri dati).
    *   Un utente Atleta che tenta di accedere a endpoint o interfacce di amministrazione/scrittura (es. builder di workout) deve ricevere un errore 403 (Access Denied).
    *   Le sessioni utente devono scadere dopo un periodo prefissato di inattività per ragioni di sicurezza.
*   **Stima:** `5 Story Points` (Media complessità; setup sicurezza e implementazione RBAC Coach/Atleta)

#### **US-D-02: Profilazione Atleta e Configurazione Soglie / Categoria**
*   **Rif. WBS/RBS:** WBS 5.2 / RBS 2.3.2.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta,
    *   *voglio* configurare le mie informazioni personali (genere, soglie cardiache di allenamento, categoria di gara Hyrox),
    *   *affinché* la dashboard calcoli correttamente le zone di intensità cardio e utilizzi i benchmark corretti per le analisi comparative.

*   **Criteri di Accettazione:**
    *   I campi obbligatori per il profilo sono: Genere (M/F), FC Max, FC di Soglia Anaerobica, Categoria di Gara (dropdown: Open, Pro, Double, Relay).
    *   Le soglie inserite devono aggiornare retroattivamente o proattivamente i report di pacing associati a quell'atleta.
    *   Inoltre grazie alla categoria di gara, la dashboard propone pesistiche in fase di creazione allenaento. 
*   **Stima:** `3 Story Points` (Bassa complessità; form di inserimento e calcolo soglie)

#### **US-D-03: Visualizzazione Comparativa Performance Team**
*   **Rif. WBS/RBS:** WBS 5.3 / RBS 2.1.1.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* visualizzare una schermata di confronto che affianchi le prestazioni e gli split times di un massimo di 4 atleti contemporaneamente per la stessa sessione,
    *   *affinché* possa confrontare i parziali delle stazioni e identificare immediatamente chi fatica di più in specifici blocchi.
*   **Criteri di Accettazione:**
    *   La dashboard deve presentare una tabella comparativa a colonne (una colonna per atleta, righe per stazioni funzionali e Roxzone).
    *   Il sistema deve evidenziare automaticamente il miglior tempo (in verde) e il peggior tempo (in rosso) per ciascun esercizio per facilitare la lettura visiva.
    *   La tabella deve supportare l'esportazione diretta in formato CSV e PDF.
*   **Stima:** `8 Story Points` (Alta complessità; confronto sincrono a 4 colonne, highlighting dinamico e logica di esportazione)

#### **US-D-04: Motore Grafici Pacing e Overlay Discrepanze**
*   **Rif. WBS/RBS:** WBS 5.4 / RBS 2.1.1.2 - 2.1.3.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* visualizzare grafici ad andamento temporale che sovrappongono il ritmo reale di corsa e delle stazioni rispetto al piano strategico di pacing ideale impostato,
    *   *affinché* possa analizzare visivamente se l'atleta ha rispettato la strategia o se è andato "fuori giri" nelle prime fasi.
*   **Criteri di Accettazione:**
    *   Il grafico deve visualizzare in ascissa (X) la progressione spaziale/temporale della sessione e in ordinata (Y) il pacing (min/km o split time).
    *   Deve esserci una linea di riferimento (Target Pacing) sovrapposta a quella reale dell'atleta.
    *   Il motore grafico deve calcolare ed evidenziare la deviazione cumulata (discrepanza) in tempo reale.
*   **Stima:** `8 Story Points` (Alta complessità; calcolo delle deviazioni spaziali/temporali e integrazione libreria chart)

#### **US-D-05: Inserimento e Gestione Sanzioni / Penalità**
*   **Rif. WBS/RBS:** WBS 5.5 / RBS 2.1.2.1 - 2.1.2.2 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* poter inserire penalità di tempo o contrassegnare no-rep per le stazioni di un allenamento terminato prima del consolidamento dei dati,
    *   *affinché* i dati archiviati riflettano l'esito reale della sessione comprensivo delle sanzioni applicate dai giudici.
*   **Criteri di Accettazione:**
    *   La dashboard deve consentire l'inserimento di penalità predefinite (es. +30s per salto Roxzone, +10s per no-rep Wall Balls) o tempi liberi su qualsiasi stazione o Roxzone.
    *   Le sanzioni inserite devono comparire in un registro modificabile associato alla sessione.
    *   Il tempo totale dell'atleta deve aggiornarsi istantaneamente riflettendo la somma algebrica del tempo di movimento e delle sanzioni.
*   **Stima:** `5 Story Points` (Media complessità; CRUD delle sanzioni e ricalcolo in tempo reale)

#### **US-D-06: Builder Pianificazione Sessioni e Gestione Template**
*   **Rif. WBS/RBS:** WBS 5.6 / RBS 2.2.1.1 - 2.2.2.1 - 2.2.2.2 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* configurare graficamente un allenamento combinando blocchi di corsa e stazioni funzionali, inserendo parametri (peso, rep, note) per ciascuno, e salvare la configurazione come template riutilizzabile,
    *   *affinché* possa pianificare sessioni strutturate e personalizzate per gli atleti riducendo i tempi di inserimento ripetitivo.
*   **Criteri di Accettazione:**
    *   Il builder deve permettere la creazione di un workout trascinando o selezionando blocchi di stazioni funzionali e corsa.
    *   Ogni blocco deve prevedere campi per: Peso (kg), Distanza (metri), Ripetizioni (numero) e Note per l'atleta (massimo 100 caratteri) - (queste verranno definite in base al tipo di attività selezionata).
    *   La funzionalità "Salva come Template" deve memorizzare la configurazione in modo persistente per consentire l'assegnazione rapida ad altri atleti o team.
*   **Stima:** `8 Story Points` (Alta complessità; interfaccia drag-and-drop del builder di workout e gestione template)

#### **US-D-07: Consultazione Dashboard in Modalità Offline**
*   **Rif. WBS/RBS:** WBS 5.7 / RBS 2.1.4.1 (Priorità: **COULD**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* visualizzare gli storici degli allenamenti e i profili degli atleti memorizzati localmente anche quando non ho connessione internet,
    *   *affinché* possa consultare i dati del team e preparare i debriefing anche durante i viaggi o in ambienti privi di copertura di rete.
*   **Criteri di Accettazione:**
    *   L'applicazione web deve implementare Service Workers e salvare i dati consultati di recente in un IndexedDB locale.
    *   Quando offline, l'utente deve visualizzare una notifica a schermo ("Modalità Offline attiva - Vista in sola lettura") e navigare tra i dati in cache senza blocchi dell'interfaccia.
*   **Stima:** `8 Story Points` (Alta complessità; setup Service Worker e IndexedDB local caching per consultazione disconnessa)

---

### 2.3 Sottosistema Sincronizzazione — *Rif. WBS 6.x / RBS Req. 3*

#### **US-S-01: Trasferimento Dati Locale Watch -> Smartphone**
*   **Rif. WBS/RBS:** WBS 6.1 / RBS 3.1.1.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta,
    *   *voglio* che i dati dell'allenamento salvati in locale sul watch vengano trasferiti in background al mio smartphone tramite Bluetooth,
    *   *affinché* l'orologio liberi memoria locale e lo smartphone possa preparare l'invio verso il cloud.
*   **Criteri di Accettazione:**
    *   Al termine della sessione (salvataggio), l'app watchOS deve instaurare automaticamente una sessione CoreBluetooth/WatchConnectivity con lo smartphone.
    *   Il trasferimento dei dati di una sessione tipo (90 minuti) deve completarsi entro 30 secondi.
    *   Il trasferimento deve supportare la ripresa automatica (resume) del download se la connettività Bluetooth si interrompe prima del completamento.
*   **Stima:** `5 Story Points` (Media complessità; protocollo CoreBluetooth e gestione sessione/resume)

#### **US-S-02: Sincronizzazione Cloud Smartphone -> Server Dashboard**
*   **Rif. WBS/RBS:** WBS 6.2 / RBS 3.2.1.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* atleta,
    *   *voglio* che i dati di sessione memorizzati sullo smartphone siano trasmessi automaticamente al cloud non appena lo smartphone rileva una connessione Internet (4G/5G/Wi-Fi),
    *   *affinché* il coach possa visualizzarli sulla dashboard senza che io debba effettuare operazioni manuali di invio.
*   **Criteri di Accettazione:**
    *   Lo smartphone deve rilevare lo stato di rete e accodare l'upload in background non appena rileva una connessione Internet stabile.
    *   L'upload deve utilizzare protocolli HTTPS sicuri e crittografare i dati sensibili degli atleti durante il transito.
    *   A caricamento completato, lo stato della sessione sullo smartphone deve cambiare in "Sincronizzato".
*   **Stima:** `5 Story Points` (Media complessità; upload HTTPS in background al ripristino connettività)

#### **US-S-03: Invio in Push del Workout Pianificato Dashboard -> Watch**
*   **Rif. WBS/RBS:** WBS 6.3 / RBS 3.3.1.1 (Priorità: **MUST**)
*   **User Story:**
    *   *Come* coach,
    *   *voglio* inviare istantaneamente il workout pianificato dalla dashboard allo smartwatch dell'atleta (passando per lo smartphone associato),
    *   *affinché* l'atleta possa iniziare la sessione programmata entro pochi secondi senza dover cercare o configurare nulla manualmente.
*   **Criteri di Accettazione:**
    *   Al click su "Invia a Watch" nella dashboard, il backend deve generare una notifica push (Apple Push Notification service - APNs) inviata allo smartphone del destinatario.
    *   Lo smartphone deve ricevere la notifica in background, svegliare l'app e spingere via Bluetooth il file di workout allo smartwatch entro un tempo target di 10 secondi totali.
    *   L'orologio deve vibrare e svegliarsi mostrando a schermo: "Nuovo allenamento ricevuto da Coach: [Nome Workout]. Avviare?".
*   **Stima:** `8 Story Points` (Alta complessità; integrazione APNs, logica di wake-up e invio bidirezionale)

---

## 3. Technical Stories (Abilitatori Tecnici)

Questi elementi rappresentano prerequisiti tecnici non direttamente associati a una funzionalità utente finale ma necessari per abilitare lo sviluppo (Spikes o Technical Tasks).

#### **US-TEC-01: Setup dell'Infrastruttura, CI/CD e Repository**
*   **Rif. WBS:** WBS 2.1 (Priorità: **MUST**)
*   **Descrizione:** Configurazione dei repository di codice (GitHub), organizzazione delle pipeline di CI/CD per il deploy automatico degli ambienti e setup del framework di sviluppo.
*   **Criteri di Accettazione:**
    *   Repository inizializzato con branching strategy definita (GitFlow).
    *   Pipeline CI/CD configurata per eseguire linter e unit test ad ogni Pull Request.
    *   Ambiente di Staging configurato e pronto per ospitare i build del backend e del frontend web.
*   **Stima:** `5 Story Points` (Media complessità; setup CI/CD, GitFlow e configurazione staging)

#### **US-TEC-02: Progettazione Architettura Dati e Cloud**
*   **Rif. WBS:** WBS 3.1 (Priorità: **MUST**)
*   **Descrizione:** Modellazione del database (relazionale o non relazionale) e definizione delle specifiche delle API RESTful per lo scambio dati tra client e server cloud.
*   **Criteri di Accettazione:**
    *   Schema ER o diagramma delle entità validato dal Tech Lead.
    *   Documentazione OpenAPI (Swagger) delle rotte API di sincronizzazione redatta e concordata tra i dev Wearable e Web.
*   **Stima:** `5 Story Points` (Media complessità; progettazione database ed esposizione endpoint Swagger)

#### **US-TEC-03: Spike Tecnologico - Raccolta Dati e Fattibilità Algoritmo**
*   **Rif. WBS:** WBS 4.4 (Priorità: **MUST**)
*   **Descrizione:** Attività di ricerca time-boxed per l'acquisizione di tracciati accelerometrici grezzi su atleti in palestra e validazione iniziale del classificatore per superare il rischio tecnologico.
*   **Criteri di Accettazione:**
    *   Almeno 10 sessioni di allenamento Hyrox registrate con dati accelerometro/giroscopio grezzi.
    *   Algoritmo preliminare testato in ambiente locale (Python/Notebook) con accuratezza minima del 70%.
    *   Documento di sintesi tecnica che definisce la fattibilità e i vincoli per l'implementazione sul watch (Sprint 6).
*   **Stima:** `5 Story Points` (Time-boxed)
