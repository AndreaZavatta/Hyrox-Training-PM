**PROJECT OVERVIEW STATEMENT**

**Project Name:** Hyrox Team Performance Optimizer	          **Project Manager:** Andrea Zavatta

**Problem/Opportunity:**

Hyrox è una disciplina atletica ibrida in cui la gestione strategica della gara e la velocità nelle transizioni incidono drasticamente sul tempo finale. Gli attuali dispositivi wearable commerciali mostrano forti limiti nel riconoscimento automatico di attività multi-esercizio strutturate. Questa carenza costringe gli atleti a interagire manualmente con lo smartwatch durante sessioni ad alta intensità cardiaca e muscolare, distogliendo il focus dal gesto atletico e penalizzando la performance stessa e i coach a operazioni manuali di editing post-allenamento della durata media di 15 minuti per atleta. Inoltre, l'assenza di metriche sincronizzate e la mancanza di strumenti per tracciare penalità di tempo e no-rep impediscono un'analisi precisa delle prestazioni del team. 

**Project Goal:**

Sviluppare, entro un arco temporale di 8 mesi, un ecosistema software integrato (Wearable App \+ Web Dashboard) per analizzare gli allenamenti o gare dei team Hyrox, automatizzando il tracciamento dei workout (pre-schedulati via dashboard) e riducendo a meno di 2 minuti i tempi di analisi post-allenamento.  

**Objectives:**

1. Sviluppo di un’ applicazione wearable comprensiva di algoritmo per il riconoscimento automatico del cambio delle stazioni hyrox basato su dati accelerometrici e sul workout pre-schedulato.  
2. Implementazione di un protocollo di sincronizzazione dati a bassa latenza per il trasferimento bidirezionale dei workout tra la piattaforma del coach e l'applicazione wearable dell'atleta (tramite smartphone).
3. Realizzazione di una Web Dashboard multipiattaforma (ottimizzata per smartphone, tablet e PC) dedicata ai coach per pianificare gli allenamenti ai team (fino a 4 atleti) e monitorarne i progressi 

   \[Nota metodologica: Sono esplicitamente esclusi dallo scope del progetto: (1) lo sviluppo di hardware proprietario, in quanto l'applicazione si appoggerà esclusivamente su dispositivi Apple Watch esistenti; (2) la funzionalità di "Free Tracking", poiché l'algoritmo richiede obbligatoriamente un workout pre-schedulato dal coach per funzionare correttamente.\] 

**Success Criteria:**

1. Validazione della precisione dell'algoritmo di riconoscimento automatico delle stazioni con un'accuratezza confermata ≥ 90%.
2. Riduzione del tempo di editing e analisi post-workout da parte del coach da 15 minuti a meno di 2 minuti nel 95% delle sessioni tracciate.   
3. Discrepanza inferiore al 2% tra il tempo totale calcolato dall'applicazione (comprensivo di transizioni e penalità) e il tempo effettivo registrato tramite cronometro ufficiale di validazione durante le simulazioni di gara.    
4. Ottenimento di un punteggio medio di usabilità pari o superiore a 80/100 (valutazione 'Eccellente') nei questionari standardizzati SUS (System Usability Scale) somministrati a un campione realistico per l'MVP di almeno 15 coach e 30 atleti. 

**Assumptions, Risks, Obstacles:**

1. **Assumption:** I coach configurino preventivamente i workout sulla piattaforma e tutti gli atleti del team monitorato (fino a 4) siano dotati fisicamente di un Apple Watch Series 6 o superiori. In caso di sincronizzazioni asincrone, la dashboard mostrerà dati parziali fino all'arrivo dei dati di tutti i membri.   
2. **Assumption:** Gli atleti seguano l'ordine dei blocchi strutturati nel workout, salvo deviazioni impreviste gestite tramite la funzione skip o riordina blocchi previste in app.   
3. **Risk (Technical):** Il rumore di fondo dei dati accelerometrici durante l'attività ad alta intensità o i limiti hardware del wearable potrebbero compromettere l'accuratezza del riconoscimento sotto la soglia critica.   
4. **Risk (Operational):** L'indisponibilità temporanea di specifici macchinari in palestra (es. SkiErg o Rower occupati) può costringere l'atleta a variare la sequenza programmata. 
5. **Risk (Technical):** Prestazioni incoerenti o malfunzionamenti legati alla frammentazione hardware di smartwatch meno recenti (watchOS).
6. **Risk (Ambientale):** Connessione internet assente o instabile durante le gare nei padiglioni fieristici o all'interno di palestre interrate.
7. **Risk (Organizzativo):** Rallentamenti nello sviluppo causati dall'abbandono di un membro del team.
8. **Risk (Culturale):** Difficoltà di adozione da parte dei coach legata alla resistenza al cambiamento degli strumenti attuali.
9. **Obstacle:** Vincolo di non sviluppare hardware proprietario; l'applicazione si appoggia esclusivamente su Apple Watch esistenti (Series 6+).
10. **Obstacle:** Vincolo ambientale di operare in modalità offline-first per far fronte alla scarsa connettività tipica di palestre e arene Hyrox.