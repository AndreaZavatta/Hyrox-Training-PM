# Working Agreements: Hyrox Team Performance Optimizer

Il presente documento definisce gli **Accordi di Lavoro (Working Agreements)** adottati dallo Scrum Team per la gestione del progetto "Hyrox Team Performance Optimizer". In linea con i principi dell'auto-organizzazione agile, questo accordo stabilisce le regole di comportamento, i protocolli di comunicazione, le cerimonie e gli standard tecnici per garantire l'efficienza del team, preservare la *Conceptual Integrity* del prodotto e facilitare il miglioramento continuo (*Kaizen*).

---

## 1. Ruoli e Responsabilità dello Scrum Team

Per evitare sovrapposizioni e definire chiaramente le sfere decisionali, il team adotta la suddivisione dei ruoli Scrum standard, declinata sul contesto del progetto:

| Ruolo | Responsabilità Principali | Autorità / Sfera Decisionale |
| :--- | :--- | :--- |
| **Product Owner (PO)** | Massimizzare il Business Value del prodotto. Gestione e prioritizzazione del Product Backlog. Interfaccia con gli stakeholder (coach esterni). | **Cosa sviluppare:** Ha l'ultima parola sulla prioritizzazione delle User Stories e sull'accettazione degli incrementi (DoD). |
| **Scrum Master (SM) / PM** | Facilitare le cerimonie Scrum. Rimuovere gli ostacoli (impediments) segnalati dal team. Garantire il rispetto della metodologia e della governance. | **Processo e Governance:** Decide come facilitare le riunioni e gestisce i rischi finanziari/temporali di macro-livello. |
| **Tech Lead (TL)** | Definire l'architettura tecnica e coordinare il team di sviluppo. Garantire l'integrità concettuale del codice e mitigare i rischi tecnologici. | **Fattibilità Tecnica:** Detiene il potere di veto su requisiti tecnicamente irrealizzabili o ad alto rischio architetturale. |
| **Dev Team (Core Team)** | Sviluppare gli incrementi di prodotto. Effettuare le stime in Story Points. Garantire la qualità del codice tramite test e peer review. | **Come sviluppare:** Ha completa autonomia sulle scelte di implementazione e sulla stima dello sforzo dei task. |

---

## 2. Ritmo di Lavoro e Cerimonie Scrum

Il progetto si sviluppa in cicli iterativi (**Sprint**) della durata fissa di **2 settimane (10 giorni lavorativi)**. Le cerimonie avvengono secondo la seguente schedulazione e regole:

### 2.1 Sprint Planning (Durata: max 2 ore - Giorno 1 dello Sprint)
*   **Partecipanti:** PO, SM, TL, Dev Team.
*   **Obiettivo:** Definire lo **Sprint Goal** e selezionare il sottoinsieme di User Story dal Product Backlog da inserire nello Sprint Backlog.
*   **Regole Operative:**
    1.  **Capacity Check:** Prima di selezionare le storie, il team calcola la capacità reale dello Sprint (giorni di presenza effettivi degli sviluppatori, escludendo ferie o impegni aziendali esterni).
    2.  **Velocity Focus:** Il team si basa sulla velocity degli Sprint precedenti per determinare quanti Story Points impegnare, senza superare la media mobile delle ultime 3 iterazioni.
    3.  **Task Breakdown:** Le User Story selezionate vengono scomposte in task tecnici di durata non superiore a 1 giorno-uomo per facilitarne il tracciamento giornaliero.

### 2.2 Daily Standup (Durata: 15 minuti rigidi - Giornaliero, ore 09:00)
*   **Partecipanti:** Dev Team, TL, SM. Il PO è invitato ma non obbligatorio.
*   **Obiettivo:** Sincronizzare le attività giornaliere e identificare eventuali blocchi (impediments).
*   **Regole Operative:**
    1.  Si svolge in piedi davanti alla *Sprint Board* (fisica o Jira).
    2.  Ciascun membro del Dev Team risponde sinteticamente a tre quesiti focalizzandosi sullo stato dei propri task:
        *   *Qual è lo stato dei miei task rispetto a ieri? (On Track / Ahead / Behind)*
        *   *Su cosa mi focalizzerò oggi?*
        *   *Ci sono ostacoli o blocchi che mi impediscono di avanzare?*
    3.  **No Problem Solving:** Il Daily Standup serve solo a evidenziare i problemi. Qualsiasi discussione tecnica o risolutiva viene rimandata a un apposito *Problem Resolution Meeting* subito dopo, coinvolgendo solo i diretti interessati.

### 2.3 Sprint Review (Durata: max 1 ora - Ultimo giorno dello Sprint)
*   **Partecipanti:** PO, SM, TL, Dev Team, Stakeholder invitati (es. Coach della palestra partner).
*   **Obiettivo:** Dimostrare il funzionamento reale dell'incremento di prodotto completato durante lo Sprint e raccogliere feedback.
*   **Regole Operative:**
    1.  Non si mostrano slide o presentazioni teoriche: la review si basa esclusivamente sulla demo live di software funzionante che soddisfa la **Definition of Done (DoD)**.
    2.  Le User Story non completate o che non rispettano la DoD non vengono mostrate e ritornano nel Product Backlog per la ri-prioritizzazione.
    3.  I feedback raccolti vengono tradotti dal PO in nuove User Story inserite nel Product Backlog.

### 2.4 Sprint Retrospective (Durata: max 1 ora - Ultimo giorno dello Sprint, post-Review)
*   **Partecipanti:** Dev Team, TL, SM, PO.
*   **Obiettivo:** Analizzare come ha funzionato il team durante lo Sprint in termini di persone, relazioni, processi e strumenti, identificando azioni concrete di miglioramento (*Kaizen*).
*   **Regole Operative:**
    1.  **Ambiente Protetto:** La discussione deve basarsi sul rispetto reciproco e sull'onestà intellettuale, senza cercare colpevoli ma analizzando le cause alla radice (approccio *5 Whys*).
    2.  **Output Azionabile:** La retrospective si conclude con la selezione di massimo **2-3 azioni concrete di miglioramento** da inserire nel backlog dello Sprint successivo, assegnandovi un responsabile.

---

## 3. Standard di Sviluppo e Collaborazione

Per mitigare i rischi tecnici e garantire la qualità del codice, il team si impegna a rispettare le seguenti regole:

### 3.1 Gestione dei Repository e Branching Strategy (GitFlow)
*   **Branch `main`:** Contiene solo codice stabile e rilasciabile in produzione. Ogni merge su `main` corrisponde ad una release ufficiale di Sprint.
*   **Branch `develop`:** Branch di integrazione principale per lo sviluppo corrente.
*   **Branch `feature/`:** Utilizzato per lo sviluppo di nuove User Story (es. `feature/US-W-01-watch-ui`) creato a partire da `develop`. Questi branch vengono integrati (merged) in `develop` **esclusivamente il lunedì**.
*   **Branch `bugfix/`:** Utilizzato per la correzione di bug ordinari identificati durante il ciclo di sviluppo. Ha la stessa funzione e ciclo di vita dei feature branch, servendo esclusivamente per categorizzare i commit. Questi branch vengono integrati in `develop` **esclusivamente il lunedì**.
*   **Branch `hotfix/`:** Utilizzato per la risoluzione urgente di anomalie critiche e bloccanti. Viene sviluppato a partire da `develop` ma, a differenza di feature e bugfix, può essere integrato (merged) in **qualsiasi giorno della settimana** per garantire la massima tempestività nel ripristino.
*   **Convenzione Commit:** I messaggi di commit devono includere l'ID della User Story o del bug di riferimento (es. `US-W-01: implementato design ad alto contrasto per la griglia esercizi`).

### 3.2 Pull Request e Peer Review
*   Nessun codice può essere unito (merged) a `develop` o `main` senza una **Pull Request (PR)**.
*   Ogni PR richiede l'approvazione di almeno **1 reviewer qualificato** (il Tech Lead o un altro sviluppatore esperto del sottosistema).
*   Il linter automatico e la suite di unit test configurati nella pipeline CI/CD devono superarsi con successo prima che la PR possa essere fusa.
*   In conformità con la DoD, la copertura dei test per la logica di business (backend, algoritmo di riconoscimento, protocolli di sync) deve essere pari o superiore all'**80%**.

### 3.3 Pair Programming Strategy
Per superare i colli di bottiglia e favorire il trasferimento di competenze, il team adotta sessioni di **Pair Programming** obbligatorie (almeno 2 ore a sessione) per lo sviluppo delle seguenti componenti critiche sul *Critical Path*:
1.  **US-W-04 (Algoritmo di Riconoscimento Sensori):** Sviluppo del modello matematico e del filtraggio dei dati grezzi.
2.  **US-S-01 / US-S-03 (Protocolli di Sincronizzazione Bluetooth/Push):** Integrazione del CoreBluetooth e gestione dello stato disconnesso/caching.
3.  **US-TEC-02 (Progettazione Architettura Dati):** Definizione dello schema e delle API per garantire la perfetta corrispondenza tra Wearable e Dashboard.

### 3.4 Knowledge Management e Allineamento Tecnico
*   Ogni venerdì alle ore 15:00 viene organizzata una sessione di **Knowledge Sharing (durata 1 ora)** in cui lo sviluppatore che ha lavorato su una feature complessa ne illustra l'architettura interna al resto del team, aggiornando il workbook di progetto.

---

## 4. Comunicazione e Gestione del Lavoro (Workbook Strategy)

Al fine di minimizzare l'overhead di comunicazione (evitando la trappola del *Mythical Man-Month* in cui aggiungere persone rallenta il progetto), si adottano le seguenti regole per i canali:

*   **Jira (Sprint Board):** È l'unica sorgente di verità per lo stato del lavoro. Nessun task può essere eseguito se non è presente sulla board. Le storie si spostano linearmente: *To Do -> In Progress -> Code Review/Test -> Done*.
*   **Slack:** Utilizzato per comunicazioni asincrone e veloci. Sono vietati i messaggi diretti per decisioni architetturali o di scope; queste discussioni devono avvenire nei canali pubblici per trasparenza:
    *   `#dev-smartwatch`: Discussione tecnica su watchOS e algoritmi sensori.
    *   `#dev-dashboard`: Discussione tecnica su web backend, frontend e grafici di pacing.
    *   `#dev-sync`: Discussione tecnica sui flussi bluetooth e API di sincronizzazione.
    *   `#general-announcements`: Notizie importanti, milestone e scadenze di Sprint.

---

## 5. Gestione dei Conflitti e Consensus Building

I conflitti tecnici e organizzativi devono essere gestiti tempestivamente per evitare di rallentare lo Sprint. Il team adotta i seguenti stili decisionali:

*   **Collaborativo (Consensus):** Utilizzato per decisioni di architettura software e design dei dati di sistema, al fine di massimizzare il buy-in di tutto il team.
*   **Consultivo:** Il Tech Lead prende le decisioni sull'infrastruttura ed il Product Owner sulle priorità di business, dopo aver ascoltato le proposte degli sviluppatori.
*   **Direttivo (Escalation Protocol):** Se non si raggiunge il consenso entro 60 minuti, si attiva il protocollo di escalation in 3 livelli definito nella metodologia:
    1.  *Livello 1:* Il PM facilita una sessione di consensus focalizzata (max 60 min).
    2.  *Livello 2 (Arbitrato):* Il Tech Lead ha l'ultima parola sui conflitti tecnologici/architetturali; il PO sui conflitti di business/priorità; il PM sui vincoli finanziari/temporali.
    3.  *Livello 3:* Conflitti che impattano > 15% del budget o > 20% della timeline sono escalati a una revisione formale con il CEO.

---

*Accordo approvato e sottoscritto dallo Scrum Team in data 20 giugno 2026.*
