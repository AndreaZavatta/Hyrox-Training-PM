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
| **Chiara Bertocchi** | Product Owner (PO) | Presentatore dei requisiti di business |
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
Lo Scrum Master ha presentato i Working Agreements definiti in fase di pianificazione, con particolare focus sui processi di:
*   **Decision Making:** Adozione dello stile partecipativo/collaborativo per l'architettura tecnica e consultivo/direttivo per le priorità di business (Product Owner).
*   **Problem Solving:** Implementazione del modello a 5 passi di Couger in caso di blocco dei task, con gestione degli impedimenti nei Daily Scrum di 15 minuti.
*   **Conflict Resolution:** Gestione dei conflitti interni tramite negoziazione cooperativa (Collaborating/Integrating) prima di scalare al Tech Lead o allo Scrum Master.

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
