**Conditions of satisfactions**

> [!TIP]
> **Miro Link:** La mappatura visuale collaborativa di questa analisi (Wants vs Needs e CoS) è consultabile sulla board: **[Miro Board - CoS & RBS](https://miro.com/app/board/uXjVHFNQqIY=/)**.

**WANTS vs NEEDS**

L'identificazione dei desiderata (Wants) è stata condotta attraverso interviste strutturate ai coach, osservazione diretta sul campo durante le sessioni di allenamento e somministrazione di sondaggi mirati agli atleti. 

### **Modulo di Profilazione e Controllo Accessi (ACL) (MUST)**

**Stakeholder Want (Coach/Atleta):** "Come coach devo poter creare e modificare i piani senza che gli atleti rischino di modificare i dati altrui. Come atleta voglio visualizzare la mia programmazione e, voglio poter inserire o correggere le mie no-rep e penalità di tempo."

**Project Manager Need:** Il sistema richiede l'implementazione di una matrice di controllo degli accessi (ACL) che si adatta dinamicamente in base al ruolo loggato: il ruolo "Coach" ha permessi di scrittura, modifica e analisi avanzata sui dati dell'intero team; il ruolo "Atleta" ha accesso in sola lettura alla programmazione e allo storico, ad eccezione dei permessi di scrittura e modifica per le proprie sanzioni e no-rep personali.

### **Configurazione Impostazioni (MUST)**

**Stakeholder Want (Atleta):** "I calcoli dell'applicazione devono basarsi sul mio reale livello di forma fisica. Voglio poter inserire le mie zone di frequenza cardiaca personali e specificare se sto gareggiando nella categoria Open, Pro, Double o Relay, così che l'app sappia esattamente quali pesi impostare di default."

**Project Manager Need:** Il sistema richiede un modulo di gestione del profilo atleta per la memorizzazione di parametri fisiologici e sportivi. L'applicazione deve calcolare le metriche di sforzo e le configurazioni standard delle stazioni di workout basandosi sulle soglie cardio immesse e sui regolamenti ufficiali della categoria selezionata (Open, Pro, Double, Relay), applicando i pesi e i volumi corrispondenti in automatico.

### **Pianificazione workout (MUST)**

**Stakeholder Want (Atleta):** "Voglio che il mio allenatore possa definire la struttura dell'allenamento prima di iniziare, in modo che io debba solo premere 'Start' sul watch senza perdere tempo a configurare stazioni o pesi"  
**Stakeholder Want (Coach):** "Voglio poter definire gli allenamenti dei miei atleti e per ogni esercizio inserire un commento che potranno visualizzare sullo smartwatch per garantire un esperienza più personalizzata possibile, inoltre vorrei aver la possibilità di creare template di allenamenti da riutilizzare per diversi atleti, senza perdere tempo a ricreare l’allenamento da capo ogni volta (utile quando gestisco molti team)”  
**Project Manager Need (Workflow di Sincronizzazione):** "Il sistema richiede un modulo di *Workout Push*. Il Coach deve poter definire una sequenza di stazioni (configurate per carico, volume e rest) tramite la Dashboard Web e la possibilità di mettere commenti opzionali su ogni stazione. Il sistema deve gestire la persistenza di questa configurazione nel Cloud e triggerare una sincronizzazione in push verso lo smartwatch dell'atleta (tramite smartphone) entro 10 secondi dalla pubblicazione, i commenti inseriti dal coach verranno visualizzati dall’atleta al momento del workout.

Inoltre, il sistema deve integrare un sotto-modulo Archivio Template sulla Dashboard Web. Questa funzionalità deve permettere al Coach di salvare qualsiasi sequenza di stazioni strutturata come modello standardizzato e riutilizzabile (es. simulazione delle 8 stazioni Hyrox), mantenendo persistenti nel Cloud l'ordine degli esercizi, i carichi minimi/massimi, i volumi e i commenti tecnici preimpostati, ovviamente per ogni team di atleti questo potrà essere personalizzato per rendere l’esperienza più personalizzata possibile."

### **Affidabilità del dato in Gara (MUST)**

**Stakeholder Want (Atleta):** *"L'app deve distinguere con precisione chirurgica quando sto cambiando esercizio, senza che io debba toccare lo schermo del mio smartwatch sotto stress."*

**Project Manager Need (Logica Applicativa):** L'applicazione necessita di un modulo logico di classificazione automatica dello stato dell'atleta. Il software deve processare flussi di dati provenienti dai sensori di movimento del dispositivo (accelerometro/giroscopio) e confrontarli con la schedulazione del workout pianificata dal coach e le soglie dinamiche di andatura e frequenza cardiaca. Il sistema deve tradurre questi dati in un cambio di stato computazionale automatizzato (Stato: *In Transito/Roxzone* vs Stato: *In Stazione Funzionale*). Accuratezza del riconoscimento automatico >= 90% sul test set senza alcun intervento manuale. Per il restante 10% (edge cases, falsi negativi), deve essere prevista una strategia di fallback manuale rapida per ricondursi all'esercizio corretto.

### **Analisi e Reporting (MUST)**  
   
**Stakeholder Want (Coach):** "Al termine dell'allenamento, desidero una visione d'insieme chiara delle performance del team su un dispositivo desktop, mobile. Devo poter contestualizzare i dati grezzi aggiungendo note tecniche, segnalando penalità (no-rep, penalità tempo) e valutando l'impatto reale di tali eventi sul tempo finale."

**Stakeholder Want (Atleta):** "Al termine dell'allenamento, desidero una visione d'insieme chiara delle mie performance sullo smartwatch e sulla dashboard web, dove voglio anche poter inserire e gestire le mie sanzioni e no-rep personali."

**Project Manager Need (Dashboard Multi-Device):** "Il sistema deve esporre un'interfaccia web-based responsive (Dashboard) accessibile via browser da dispositivi mobile e desktop. La Dashboard deve permettere la visualizzazione aggregata delle metriche di gara (Pacing, Heart Rate, Split Times) e l'inserimento/gestione di no-rep e sanzioni di tempo (sia per il coach sul team, sia per l'atleta sulla propria sessione). Il sistema deve garantire la persistenza dei dati dell'allenamento.  
Inoltre deve esserci una funzionalità a livello di smartwatch per vedere un riepilogo con gli split time con i tempi di ogni stazione di workout.”

### **Flessibilità negli Allenamenti (COULD)**

**Stakeholder Want (Atleta):** *"In palestra capita che un macchinario sia occupato. Voglio poter cambiare una stazione o cambiare l'ordine degli esercizi senza che l'applicazione mi rovini i grafici della sessione."*

**Project Manager Need (Workflow di Processo):** L'applicazione deve consentire il riordino o il cambio di una stazione tramite un massimo di 2 interazioni (touch o fisiche tramite bottoni).  
### **Usabilità sotto stress (MUST)**

**Stakeholder Want (Atleta):** *"Durante la gara sono completamente in affanno; lo schermo dell'orologio deve essere leggibile con un colpo d'occhio immediato."*

**Project Manager Need (Interfaccia e Usabilità):** Garantire che l'interfaccia dell'applicazione su smartwatch sia pienamente fruibile dall'atleta in condizioni di sforzo fisico estremo, eliminando qualsiasi carico cognitivo superfluo. L'obiettivo è permettere all'atleta di monitorare le metriche di gara essenziali in tempi minimi, assicurando la sicurezza e la continuità della performance senza distrazioni.

### **Continuità Operativa (SHOULD)**

**Stakeholder Want (Coach/Atleta):** *"Le palestre e le arene di gara spesso sono dei seminterrati o dei capannoni isolati dove internet non prende. Il sistema non deve perdere nemmeno un secondo di tracciamento se salta la connessione."* 

**Project Manager Need (Architettura del Workflow):** Implementazione di logica *Offline-First*. Il sistema deve supportare il caching locale di almeno 4 ore di allenamento. La sincronizzazione cloud deve completarsi entro 5 secondi dal ripristino della connettività, con una perdita di dati < 1%.

### **Dashboard Offline-First / Local View (COULD)**

* **Stakeholder Want (Coach):** "Quando sono in zone con zero connettività (es. scantinati o zone remote), vorrei poter consultare i dati di sintesi del team memorizzati localmente sul mio tablet, senza dover attendere il ripristino della rete."  
* **Project Manager Need (Modulo Dashboard Offline):** Il sistema *potrebbe* prevedere una modalità di visualizzazione "Offline-Cache" nell'applicazione Web. Questa funzionalità permetterebbe di accedere in sola lettura a un set limitato di dati (ultimi 10 allenamenti sincronizzati) salvati nel browser.

### **Sviluppo di Hardware Proprietario (WON'T)**

* **Stakeholder Want:** "Per ottenere la massima precisione possibile, si potrebbe creare un hardware personalizzato (smartwatch proprietario) dedicato esclusivamente al tracciamento delle performance durante l'allenamento hyrox."  
* **Project Manager Need (Esclusione Scope \- Out of Scope):** Lo sviluppo, la prototipazione e la produzione di un hardware personalizzato (smartwatch dedicato) sono **esplicitamente esclusi dallo scope del progetto**. Il sistema sarà sviluppato esclusivamente come applicazione software per dispositivi esistenti (Apple Watch).

### **Free Tracking (WON'T)**

* **Stakeholder Want (Atleta):** "Vorrei poter premere start sull'orologio senza che il coach mi abbia assegnato un workout, e avere l'orologio che indovina magicamente gli esercizi che decido di fare sul momento."
* **Project Manager Need (Esclusione Scope - Out of Scope):** Lo sviluppo di un algoritmo in grado di riconoscere in modo assoluto e senza contesto gli esercizi (Free Tracking) è **esplicitamente escluso dallo scope del progetto**. Il tracciamento automatico richiede obbligatoriamente un workout pre-schedulato dal coach come baseline.
