# Working Agreements

Il presente documento definisce gli **Accordi di Lavoro (Working Agreements)** adottati dallo Scrum Team per la gestione del progetto "Hyrox Team Performance Optimizer". Questo accordo stabilisce le regole di comportamento, i protocolli di comunicazione, le cerimonie e gli standard tecnici.

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
    1.  Non si mostrano presentazioni: la review si basa esclusivamente sulla demo live di software funzionante che soddisfa la **Definition of Done (DoD)**.
    2.  Le User Story non completate o che non rispettano la DoD non vengono mostrate e ritornano nel Product Backlog per la ri-prioritizzazione.
    3.  I feedback raccolti vengono tradotti dal PO in nuove User Story inserite nel Product Backlog.

### 2.4 Sprint Retrospective (Durata: max 1 ora - Ultimo giorno dello Sprint, post-Review)
*   **Partecipanti:** Dev Team, TL, SM, PO.
*   **Obiettivo:** Analizzare come ha funzionato il team durante lo Sprint in termini di persone, relazioni, processi e strumenti, identificando azioni concrete di miglioramento (*Kaizen*).
*   **Regole Operative:**
    1.  **Ambiente Protetto:** La discussione deve basarsi sul rispetto reciproco e sull'onestà, senza cercare colpevoli ma analizzando le cause alla radice (approccio *5 Whys*).
    2.  **Output Azionabile:** La retrospective si conclude con la selezione di massimo **2-3 azioni concrete di miglioramento** da inserire nel backlog dello Sprint successivo, assegnandovi un responsabile.

---

## 3. Comunicazione e Gestione del Lavoro (Workbook Strategy)

Al fine di minimizzare l'overhead di comunicazione, si adottano le seguenti regole per i canali:

*   **Jira (Sprint Board):** È l'unica sorgente di verità per lo stato del lavoro. Nessun task può essere eseguito se non è presente sulla board. Le storie si spostano linearmente: *To Do -> In Progress -> Test Business -> Test Technical-> Done*.
*   **Microsoft Teams:** Utilizzato per comunicazioni asincrone e veloci. Sono vietati i messaggi diretti per decisioni architetturali o di scope; queste discussioni devono avvenire nei gruppi per trasparenza:
    *   `dev-smartwatch`: Discussione tecnica su watchOS e algoritmi sensori.
    *   `dev-dashboard`: Discussione tecnica su web backend, frontend e grafici di pacing.
    *   `dev-sync`: Discussione tecnica sui flussi bluetooth e API di sincronizzazione.
    *   `general-announcements`: Notizie importanti, milestone e scadenze di Sprint.

---

## 4. Gestione dei Conflitti e Consensus Building

I conflitti tecnici e organizzativi devono essere gestiti tempestivamente per evitare di rallentare lo Sprint. Il team adotta i seguenti stili decisionali:

*   **Collaborativo (Consensus):** Utilizzato per decisioni di architettura software e design dei dati di sistema. Il team raggiunge il consenso attraverso la discussione aperta.
*   **Consultivo:** Il decisore raccoglie input da tutti i membri coinvolti prima di decidere. Utilizzato per decisioni tecniche complesse (Tech Lead consulta il team) o di priorità (PO consulta stakeholder e team).
*   **Direttivo (Escalation Protocol):** Se non si raggiunge il consenso entro 60 minuti, si attiva il protocollo di escalation in 2 livelli:
    1.  *Livello 1:* Il ruolo competente decide autonomamente in base alla sfera di autorità: Tech Lead per conflitti tecnologici/architetturali; PO per conflitti di business/priorità; PM per vincoli finanziari/temporali.
    2.  *Livello 2:* Conflitti che impattano > 15% del budget o > 20% della timeline sono escalati formalmente al CEO con raccomandazione del PM.

---

*Accordo approvato e sottoscritto dallo Scrum Team in data 20 gennaio 2026:*

*   **Chiara Bertocchi** (Product Owner)
*   **Andrea Zavatta** (Scrum Master / PM)
*   **Giovanni Manca** (Technical Leader & ML Specialist)
*   **Luca Pasini** (Senior Wearable Developer)
*   **Francesca Gaeta** (Senior Frontend Developer)
*   **Marco Antolini** (Backend & Database Developer)
*   **Giulia Fabbri** (Mobile Integration Specialist / QA)
