
# PROJECT DEFINITION STATEMENT (PDS)

**Project Name:** Hyrox Team Performance Optimizer  
**Project Manager:** Andrea Zavatta  
**Metodologia PMLC:** Iterativo (Scrum)  

---

## 1. Problem/Opportunity

Hyrox è una disciplina atletica ibrida in cui la gestione strategica della gara e la velocità nelle transizioni incidono drasticamente sul tempo finale. Gli attuali dispositivi wearable commerciali mostrano forti limiti nel riconoscimento automatico di attività multi-esercizio strutturate. Questa carenza costringe gli atleti a interagire manualmente con lo smartwatch durante sessioni ad alta intensità cardiaca e muscolare, distogliendo il focus dal gesto atletico e penalizzando la performance stessa e i coach a operazioni manuali di editing post-allenamento della durata media di 15 minuti per atleta. Inoltre, l'assenza di metriche sincronizzate e la mancanza di strumenti per tracciare penalità di tempo e no-rep impediscono un'analisi precisa delle prestazioni del team.

**Dettaglio operativo per il team:**  
L'analisi condotta durante lo Scoping Meeting ha evidenziato tre aree critiche su cui il team dovrà concentrare l'effort:

* **Carico cognitivo dell'atleta (Wearable):** I wearable commerciali non sono in grado di distinguere automaticamente le 8 stazioni funzionali Hyrox dalle fasi di corsa (Roxzone). Questo costringe l'atleta a toccare manualmente lo schermo del watch — un'operazione critica quando si è sotto sforzo estremo, con mani bagnate di sudore e frequenza cardiaca elevata. Il Business Value dell'eliminazione di questo carico è direttamente legato alla CoS "Affidabilità del dato in Gara" (MUST).

* **Inefficienza operativa del coach (Dashboard):** I coach dedicano in media 15 minuti per atleta post-sessione per editing manuale dei dati (video, tempi, metriche aggregate). Con team di 4 atleti, questo si traduce in circa 60 minuti di lavoro non scalabile per ogni allenamento. Il Business Value della Dashboard è il risparmio medio di 13 minuti di editing per sessione per atleta (vedi RBS Requisito 3).

* **Assenza di tracciamento team (Sincronizzazione):** Non esiste attualmente un sistema per aggregare in tempo reale i dati di più atleti, tracciare penalità di tempo e no-rep, e produrre analisi comparative di pacing. Questo impedisce al coach di prendere decisioni informate durante e dopo l'allenamento.

---

## 2. Project Goal

Sviluppare, entro un arco temporale di 8 mesi, un ecosistema software integrato (Wearable App + Web Dashboard) per analizzare gli allenamenti o gare dei team Hyrox, automatizzando il tracciamento dei workout (pre-schedulati via dashboard) e riducendo a meno di 2 minuti i tempi di analisi post-allenamento.

**Dettaglio operativo per il team:**  
Il sistema che il team andrà a realizzare si compone di **tre sottosistemi principali**, come definito dalla Requirements Breakdown Structure (RBS):

1. **Sistema di Riconoscimento ed Analisi Automatica Esercizi (Smartwatch Atleta):**  
   Applicazione nativa watchOS per Apple Watch Series 6+ che integra un algoritmo di classificazione inerziale (accelerometro/giroscopio) in grado di distinguere automaticamente le fasi di corsa (Roxzone) dalle stazioni funzionali Hyrox, confrontando i dati sensoriali con la schedulazione del workout. L'app include la UI ottimizzata per uso sotto sforzo, la visualizzazione delle note del coach, il report locale post-workout e il caching offline-first.

2. **Applicazione Web Dashboard (Coach e Atleta):**  
   Portale web responsive (smartphone, tablet, PC) suddiviso in tre macro-funzionalità: (a) dashboard di monitoraggio team con split times comparativi, grafici di pacing overlay e gestione sanzioni/no-rep (sia per il coach sul team, sia per l'atleta sulla propria sessione); (b) costruttore visuale di workout con gestione template; (c) sistema di profilazione e ACL con ruoli differenziati Coach (scrittura/analisi) e Atleta (lettura storico, programmazione e inserimento/modifica delle proprie sanzioni personali).

3. **Sottosistema di Sincronizzazione Dati:**  
   Protocollo bidirezionale a bassa latenza per il trasferimento dei workout dalla dashboard allo smartwatch (via smartphone) e il ritorno dei dati di sessione dallo smartwatch al cloud del coach. L'architettura è progettata offline-first: i dati vengono memorizzati localmente sul watch e sincronizzati via Bluetooth allo smartphone, che a sua volta li trasmette al cloud non appena è disponibile una connessione stabile.

\[Nota metodologica: Sono esplicitamente esclusi dallo scope del progetto: (1) lo sviluppo di hardware proprietario, in quanto l'applicazione si appoggerà esclusivamente su dispositivi Apple Watch esistenti; (2) la funzionalità di "Free Tracking", poiché l'algoritmo richiede obbligatoriamente un workout pre-schedulato dal coach per funzionare correttamente.\]

---

## 3. Project Objectives

1. Sviluppo di un'applicazione wearable comprensiva di algoritmo per il riconoscimento automatico delle stazioni hyrox basato su dati accelerometrici e sul workout pre-schedulato.
2. Implementazione di un protocollo di sincronizzazione dati a bassa latenza per il trasferimento bidirezionale dei workout tra la piattaforma del coach e l'applicazione wearable dell'atleta.
3. Realizzazione di una Web Dashboard multipiattaforma (ottimizzata per smartphone, tablet e PC) dedicata ai coach per pianificare gli allenamenti ai team (fino a 4 atleti) e monitorarne i progressi.

**Dettaglio operativo per il team:**  
Ciascun obiettivo viene scomposto dall'RBS in funzioni, sotto-funzioni e feature misurabili, prioritizzate secondo MoSCoW. Di seguito la mappatura completa che il team utilizzerà come baseline per la costruzione della WBS e del Product Backlog.

### Obiettivo 1 — Applicazione Wearable (RBS Requisito 1)

| ID | Sotto-funzione / Feature | Priorità | CoS di Riferimento |
| :--- | :--- | :--- | :--- |
| 1.1.1.1 | Skip della stazione corrente con selezione alternativa | COULD | Flessibilità negli Allenamenti |
| 1.1.1.2 | Funzione "Riordina Blocchi" per sequenza differente | COULD | Flessibilità negli Allenamenti |
| 1.1.1.3 | Funzionalità di transizione manuale (Fallback Trigger) a basso carico cognitivo | MUST | Affidabilità del dato in Gara |
| 1.1.2.1 | Algoritmo di riconoscimento automatico cambio stazione via sensori e schedulazione workout | MUST | Affidabilità del dato in Gara |
| 1.1.3.1 | Visualizzazione dinamica delle note testuali del coach sulla stazione attiva | MUST | Pianificazione workout |
| 1.1.4.1 | Report locale post-attività con split times delle 8 stazioni e tempi di transizione | MUST | Analisi e Reporting |
| 1.1.5.1 | Memorizzazione locale e continua dei dati biometrici e di movimento in assenza di rete | SHOULD | Continuità Operativa |
| 1.1.6.1 | Interfacce ad alto contrasto per usabilità sotto sforzo (SUS Score >= 80/100) | MUST | Usabilità sotto stress |


### Obiettivo 2 — Web Dashboard (RBS Requisito 2)

| ID | Sotto-funzione / Feature | Priorità | CoS di Riferimento |
| :--- | :--- | :--- | :--- |
| 2.1.1.1 | Tabella comparativa split times per 4 atleti post-sincronizzazione | MUST | Analisi e Reporting |
| 2.1.1.2 | Grafici di pacing sovrapposti (andatura ideale vs reale) | MUST | Analisi e Reporting |
| 2.1.1.3 | Dashboard visibile sia dal coach (con commenti) sia dagli atleti | MUST | Analisi e Reporting |
| 2.1.2.1 | Gestione sanzioni standard Hyrox (tempo, no-rep) | MUST | Analisi e Reporting |
| 2.1.2.2 | Registro cronologico sanzioni con modifica/cancellazione pre-report | MUST | Analisi e Reporting |
| 2.1.3.1 | Overlay tempo reale (con sanzioni) vs tempo potenziale "pulito" | MUST | Analisi e Reporting |
| 2.1.4.1 | Modalità Offline-Cache per visualizzazione locale della Dashboard | COULD | Dashboard Offline-First / Local View |
| 2.2.1.1 | Interfaccia a blocchi per le 8 stazioni con campi editabili (peso, distanza, reps) | MUST | Pianificazione workout |
| 2.2.2.1 | Salvataggio Template per riutilizzo rapido | MUST | Pianificazione workout |
| 2.2.2.2 | Note testuali del coach per stazione, visibili sul watch | MUST | Pianificazione workout |
| 2.3.1.1 | Registrazione e login | MUST | Profilazione e ACL |
| 2.3.1.2 | Profilazione differenziata Coach (scrittura/analisi) vs Atleta (lettura e modifica proprie sanzioni) | MUST | Profilazione e ACL |
| 2.3.2.1 | Configurazione soglie cardio e categoria di gara (Open, Pro, Double, Relay) | MUST | Configurazione Impostazioni |

---

### Obiettivo 3 — Protocollo di Sincronizzazione (RBS Requisito 3)

| ID | Sotto-funzione / Feature | Priorità | CoS di Riferimento |
| :--- | :--- | :--- | :--- |
| 3.1.1.1 | Trasferimento dell'intera sessione di allenamento da watch a smartphone a fine attività | MUST | Analisi e Reporting |
| 3.2.1.1 | Trasmissione remota dei dati consolidati da smartphone atleta a dashboard Coach | MUST | Analisi e Reporting |
| 3.3.1.1 | Trasferimento in push del piano di allenamento da Dashboard a watch entro 10s | MUST | Pianificazione workout |

## 4. Success Criteria

1. **Riduzione tempo operativo:** Riduzione del tempo di editing e analisi post-workout da parte del coach da 15 minuti a meno di 2 minuti nel 95% delle sessioni tracciate.
2. **Precisione temporale:** Discrepanza inferiore al 2% tra il tempo totale calcolato dall'applicazione (comprensivo di transizioni e penalità) e il tempo effettivo registrato tramite cronometro ufficiale di validazione durante le simulazioni di gara.
3. **Usabilità:** Ottenimento di un punteggio medio di usabilità pari o superiore a 80/100 (valutazione 'Eccellente') nei questionari standardizzati SUS (System Usability Scale) somministrati a un campione di almeno 15 coach e 30 atleti.

**Dettaglio operativo per il team — Protocollo di Validazione:**  
La verifica dei Success Criteria avverrà in due fasi empiriche:

* **Lab Testing (Fasi finali di sviluppo):** Test in palestra controllata con macchinari Hyrox dedicati. Metriche target: accuracy dell'algoritmo ≥ 90%, latenza di sincronizzazione e battery drain su sessioni di 90 minuti.
* **Field Testing (Prima del rilascio):** Condizioni di gara reali o simulate con 15 coach e 30 atleti. Metriche target: discrepanza tempo < 2%, SUS Score ≥ 80/100, tempo medio di analisi post-workout < 2 minuti.

Il **Go/No-Go Protocol** prevede che al completamento del PoC, se l'algoritmo non raggiunge un'accuratezza accettabile (target > 90%), si attivi il "Pivot to Plan B" con implementazione di un Manual Trigger (vedi sezione Rischi).

---

## 5. Assumptions, Risks, Obstacles

### Assumptions
1. I coach configurino preventivamente i workout sulla piattaforma e gli atleti utilizzino Apple Watch Series 6 o superiori.
2. Gli atleti seguano l'ordine dei blocchi strutturati nel workout, salvo deviazioni impreviste gestite dall'algoritmo.

### Risks

**Dettaglio operativo per il team:**  
I rischi sono stati classificati in base alla probabilità di accadimento (1-5) e all'impatto sul business value finale (1-5). Il Risk Score è calcolato come R = P × I. Di seguito i rischi identificati:

| Categoria | Descrizione | P | I | Score | Mitigazione |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Tecnologico** | Il sistema potrebbe non riconoscere correttamente alcuni esercizi (es. confusione Sled Push vs Sled Pull). Il rumore di fondo dei dati accelerometrici durante attività ad alta intensità potrebbe compromettere l'accuratezza sotto la soglia critica. | 4 | 5 | **20** | Sviluppo di un sistema di "correzione rapida" sull'orologio + Spike/PoC nelle prime iterazioni per validare la fattibilità tecnica. Se PoC insufficiente: attivazione **Plan B (Manual Trigger)**. |
| **Tecnologico** | Prestazioni incoerenti tra diversi modelli di smartwatch (versioni vecchie vs nuove). | 4 | 3 | 12 | Definizione di una lista di "Dispositivi Certificati" (Apple Watch Series 6+). Test su hardware differenti acquisiti dal progetto. |
| **Ambientale** | Connessione instabile o assente nei padiglioni fieristici e nelle palestre (seminterrati, capannoni). | 3 | 3 | 9 | Architettura **Offline-First**: l'orologio salva i dati nella memoria interna. Trasferimento via Bluetooth a fine gara, poi upload al cloud appena disponibile connessione stabile. |
| **Ambientale** | Un membro del team abbandona il progetto durante lo sviluppo. | 2 | 4 | 8 | Documentazione rigorosa, Pair Programming obbligatorio su task critici, Knowledge Sharing Sessions settimanali. |
| **Culturale** | Gli allenatori preferiscono gli strumenti attuali o trovano la nuova dashboard estranea. | 2 | 5 | 10 | Coinvolgimento attivo di un gruppo di coach fin dallo Scoping Meeting. Sondaggi e interviste per validare i processi attuali. |
| **Operativo** | L'indisponibilità temporanea di specifici macchinari in palestra può costringere l'atleta a variare la sequenza programmata. | 3 | 3 | 9 | Implementazione delle feature di "Flessibilità" (COULD): Skip, Riordina Blocchi. |

### Gestione del Rischio Critico (Score = 20): Piano B "Manual Trigger"

Il rischio tecnologico sull'accuratezza dell'algoritmo (Score = 20, area rossa della Heatmap) è il rischio a più alta priorità del progetto e impatta direttamente il raggiungimento del Project Goal. La strategia di gestione si divide in:

* **Analisi Preventiva (Prime iterazioni):** Verrà condotta una Proof of Concept (PoC) tramite uno Spike dedicato nelle prime iterazioni. L'obiettivo è validare la fattibilità tecnica e stabilire una baseline di accuratezza.
* **Gate Go/No-Go (Post-PoC):** Se l'accuratezza non raggiunge il 90%, il Tech Lead esercita il potere di veto (come da protocollo di escalation) e si attiva il Plan B.
* **Plan B — Manual Trigger:** Un'interazione manuale a basso carico cognitivo adatta all'uso sotto sforzo estremo:
    * **Interazione a basso carico cognitivo:** Elementi interattivi semplici (es. bottoni laterali dello smartwatch piuttosto che tocco dello schermo, che potrebbe essere bagnato dal sudore).
    * **Feedback Immediato:** Il sistema deve fornire un feedback immediato del cambio esercizio, riducendo la frustrazione e mantenendo alto il Business Value percepito.
    * **Fallback Immediato:** In caso di errore nell'input manuale (cambio esercizio sbagliato), deve esistere una funzione "Undo" altrettanto rapida.

### Obstacles
* **Vincolo hardware:** Nessun hardware proprietario; l'applicazione si appoggia esclusivamente su Apple Watch esistenti, con i relativi limiti di sensori, batteria e potenza computazionale.
* **Vincolo ambientale:** Le palestre e le arene Hyrox sono spesso in ambienti con scarsa connettività (seminterrati, capannoni), rendendo obbligatoria l'architettura offline-first.
* **Vincolo temporale:** L'arco temporale di 8 mesi include la fase di validazione sul campo (Lab Testing + Field Testing), che richiede coordinamento con coach e atleti esterni al team.

