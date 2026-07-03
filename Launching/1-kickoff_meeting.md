# Verbale del Project Kick-Off Meeting

**Progetto:** Hyrox Team Performance Optimizer  
**Data:** 2 Febbraio 2026  
**Orario:** 09:30 - 11:30  
**Luogo:** Miro Board / Team War Room Cesena  
**Stato:** Approvato per l'esecuzione  

---

## 1. Partecipanti e Ruoli (Scrum Team)

| Nominativo | Ruolo nel Progetto | Ruolo nel Kick-Off |
| :--- | :--- | :--- |
| **Chiara Bertocchi** | Product Owner (PO) & Project Sponsor | Presentatore dei requisiti di business e Sponsor/Committente (titolare del Box Hyrox partner) |
| **Andrea Zavatta** | Scrum Master (SM) / Project Manager | Facilitatore del meeting e garante della metodologia |
| **Giovanni Manca** | Technical Leader (TL) & ML Specialist | Rappresentante dell'architettura e responsabile scientifico dell'algoritmo di classificazione (Machine Learning & Sensor Fusion) |
| **Luca Rossi** | Senior Wearable Developer (iOS/watchOS) | Stima complessità wearable e caching locale |
| **Elena Bianchi** | Senior Frontend Developer (React Web) | Stima complessità dashboard e visualizzazione dati |
| **Matteo Neri** | Backend & Database Developer | Stima complessità DB, REST API e schema ER |
| **Sara Viola** | Mobile Integration Specialist / QA Tester | Stima sincronizzazione Bluetooth e testing di usabilità |

---

## 2. Agenda del Meeting

1.  **Introduzione e Visione del Prodotto:** Allineamento del team sulla Product Vision definita nel PDS.
2.  **Obiettivi e Criteri di Successo:** Revisione dell'efficacia per i coach (post-workout < 2 minuti) e accuratezza dell'algoritmo (discrepanza < 2%).
3.  **Metodologia Ibrida e Governance:** Presentazione delle regole operative del team, DoD/DoR e cerimonie Scrum.
4.  **Discussione dei Rischi Critici:** Focus sul rischio tecnologico dell'algoritmo watchOS e pianificazione dello Spike.
5.  **Pianificazione e Roadmap:** Allineamento sugli 8 mesi di sviluppo (16 Sprint) e le 3 release principali.
6.  **Domande, Risposte e Approvazione Formale:** Firma del PDS per l'avvio formale della Fase Esecutiva (Launching).

---

## 3. Punti Trattati e Decisioni Prese

### 3.1 Allineamento sulla Product Vision (PDS)
Il Product Owner (Chiara) ha illustrato al team di sviluppo le frustrazioni vissute quotidianamente nel suo box Hyrox: l'inefficacia della raccolta dati manuale (15 minuti per atleta post-workout) e la difficoltà degli atleti nel tracciare gli split sotto sforzo estremo. 
Il team ha approvato e sottoscritto la **Product Vision**: sollevare l'atleta dal tracciamento manuale sul watch e automatizzare la visualizzazione comparativa del pacing per il coach sulla dashboard in meno di 2 minuti.

### 3.2 Formalizzazione delle Regole Operative del Team (Working Agreements)
Lo Scrum Master ha presentato i Working Agreements definiti in fase di pianificazione, dettagliando l'applicazione delle regole operative richieste per la fase di esecuzione (dispensa Teoria/8):
*   **Decision Making & Consensus Building:**
    *   *Stile decisionale:* Si adotta lo stile *collaborativo/partecipativo* per le decisioni di architettura software e design dei dati (coinvolgendo l'intero team per stimolare l'ingegno collettivo) e lo stile *consultivo/direttivo* per la prioritizzazione del Product Backlog (in capo al Product Owner).
    *   *Avviso di Wysocki sul Consensus:* Il team accetta l'avvertimento formale della teoria: un consenso forzato che cerca di soddisfare equamente tutti i membri può tradursi in una decisione debole o compromissoria. Qualora non si raggiunga il consenso entro 60 minuti di discussione, si attiva il protocollo di escalation: l'arbitrato finale spetta al Tech Lead per i conflitti tecnologici, al PO per quelli di business e al PM per i vincoli di budget/tempo.
*   **Problem Solving:**
    *   Si adotta il **modello a 5 passi di Daniel Couger**:
        1. *Definizione del problema* e identificazione del proprietario (owner).
        2. *Raccolta dei dati rilevanti* e analisi delle cause radice (Root Cause Analysis).
        3. *Generazione di idee e soluzioni alternative* tramite brainstorming.
        4. *Valutazione e prioritizzazione* delle soluzioni identificate.
        5. *Sviluppo di un piano d'azione* per l'implementazione e successiva verifica.
*   **Conflict Resolution:**
    *   I conflitti costruttivi sul codice o sul design sono incoraggiati, ma devono essere risolti tramite negoziazione cooperativa ed empatia (*Collaborating/Integrating*). Atteggiamenti di dominazione (*Competing*) o di indifferenza (*Avoiding*) verranno mitigati dal Scrum Master per tutelare il clima di squadra.
*   **Brainstorming Method:**
    *   Per la progettazione dei moduli più complessi (es. l'algoritmo di machine learning e la sincronizzazione bluetooth), il team adotta la tecnica del brainstorming formale: riunione mirata dei tecnici competenti, sospensione di qualsiasi giudizio critico iniziale per permettere la libera generazione di idee, discussione aperta di tutte le proposte emerse e test mentale delle alternative fino alla convergenza sulla soluzione migliore.
*   **Linee Guida per la Gestione delle Riunioni (Meeting Management):**
    *   *Before:* Lo Scrum Master verificherà la reale necessità di ogni incontro; definirà chiaramente lo scopo e inviterà esclusivamente le risorse indispensabili, inviando l'agenda con anticipo.
    *   *During:* Verranno rispettati rigorosamente l'orario di inizio e la durata pianificata (timebox); si utilizzeranno supporti visivi (Miro, Jira Board); si eviteranno digressioni personali focalizzandosi sugli obiettivi.
    *   *After:* Ogni riunione si chiuderà con la definizione di azioni concrete (*Action Items*), assegnazione dei responsabili e scadenze. Il verbale (curato dallo Scrum Master) sarà pubblicato su Confluence ed entro la fine di ciascun meeting verranno stabiliti i partecipanti e gli obiettivi della riunione successiva.
    *   *Tipologie di Meeting:*
        1. *Daily Status (Daily Scrum):* 15 minuti giornalieri rigidi, in piedi. Si risponde a: *Cosa ho fatto, cosa farò, quali impedimenti ho*. Le discussioni tecniche risolutive sono tassativamente escluse e rimandate.
        2. *Problem Resolution Meeting:* Incontri ad-hoc per risolvere blocchi complessi emersi nel Daily, coinvolgendo solo i diretti interessati.
        3. *Project Review Meeting (Sprint Review):* Evento formale al termine dello Sprint per mostrare la demo del software funzionante al PO, allo Sponsor e ai Coach esterni, analizzando le metriche e raccogliendo i feedback.

### 3.3 Gestione dei Rischi Critici & Strategia di Spike
Il Tech Lead ha sollevato il tema del **rischio di activity recognition (Risk Score: 20)**. Viene concordata la seguente strategia:
1.  Lo **Sprint 4** sarà dedicato esclusivamente a uno **Spike Tecnologico (US-TEC-03)**: il team raccoglierà i dati inerziali grezzi (accelerometro e giroscopio) su 10 atleti durante allenamenti reali per definire la fattibilità matematica.
2.  I costi dello Spike e dei test preliminari saranno coperti dalla **Riserva di Contingenza (€24.700)**.
3.  Viene stabilito il **Gate Go/No-Go allo Sprint 12**: se la precisione dell'algoritmo in laboratorio sarà inferiore al 90%, si attiverà immediatamente il *Pivot al Plan B (Manual Trigger)*, modificando l'interfaccia watchOS per l'avanzamento manuale a bassissimo carico cognitivo (Digital Crown + tasto laterale).

### 3.4 Roadmap dei Rilasci e Disponibilità delle Risorse
Il team ha validato la pianificazione dei 16 Sprint strutturata su 3 release principali:
*   **Release 1 (Sprint 1-8):** MVP Core (DB, Builder, UI Watch, Algo Core e sync Bluetooth).
*   **Release 2 (Sprint 9-11):** Advanced Analytics (confronto team, sanzioni e dashboard offline).
*   **Release 3 (Sprint 12-16):** Validation (Lab testing, usabilità SUS, store submission e deploy).

Tutte le risorse umane (PM, PO, Tech Lead e i 4 sviluppatori) hanno confermato la piena disponibilità per il monte ore pianificato (€29.000/mese di budget HR).

---

## 4. Matrice di Assegnazione delle Responsabilità (RASCI)

Per garantire la massima chiarezza sui deliverable di avvio, viene condivisa la matrice delle responsabilità per la fase di Launching:

| Attività / Deliverable | Chiara (PO) | Andrea (SM) | Giovanni (TL) | Dev Team |
| :--- | :---: | :---: | :---: | :---: |
| **Approvazione PDS** | **A** | **C** | **I** | **I** |
| **Scrittura Work Packages** | **I** | **R** | **R** | **S** |
| **Setup Repository & CI/CD** | **I** | **I** | **A** | **R** |
| **Data Collection (Spike)** | **C** | **S** | **A** | **R** |
| **Gestione Change Requests** | **A** | **R** | **C** | **I** |

*Legenda: **R**esponsible, **A**ccountable, **S**upport, **C**onsulted, **I**nformed.*

---

## 5. Prossimi Passi (Action Items)

| ID | Attività | Assegnato a | Scadenza | Stato |
| :--- | :--- | :--- | :---: | :---: |
| **ACT-01** | Firma formale del Project Definition Statement (PDS). | Chiara, Andrea | 03 Feb 2026 | In Corso |
| **ACT-02** | Creazione dei Work Packages dettagliati per le prime storie core. | Andrea, Giovanni | 05 Feb 2026 | In Corso |
| **ACT-03** | Inizializzazione dei repository Git e configurazione pipeline CI/CD (US-TEC-01). | Dev Team | 08 Feb 2026 | Da Iniziare |
| **ACT-04** | Preparazione del materiale hardware per i test inerziali (Apple Watch di test). | Andrea | 10 Feb 2026 | Da Iniziare |

---

*Il PDS è stato ufficialmente firmato dai rappresentanti delle parti al termine dell'incontro. Il progetto entra ufficialmente nella sua fase esecutiva.*
