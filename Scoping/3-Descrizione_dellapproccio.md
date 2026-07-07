# **Descrizione dell'Approccio Metodologico**

Questo documento sintetizza l'approccio metodologico **Ibrido (Agile/Tradizionale)** adottato per la gestione del progetto "Hyrox Team Performance Optimizer". L'obiettivo è unire la flessibilità esecutiva del framework Scrum con il rigore documentale del Project Management tradizionale, necessario per garantire tracciabilità e controllo finanziario.

---

## **1. Scoping e Planning (Approccio Predittivo)**
Le fasi iniziali seguono un approccio strutturato per garantire l'allineamento strategico e la definizione del perimetro (Scope):
*   **Documentazione Formale:** Redazione di POS (Project Overview Statement) e PDS (Project Definition Statement) per definire criteri di successo misurabili e vincoli di budget/tempo.
*   **WBS e Backlog:** I requisiti vengono scomposti in una WBS orientata ai deliverable e tradotti in un Product Backlog stimato in Story Points (SP).
*   **Baseline:** Viene definita una Release Roadmap a capacità fissa (16 Sprint, 8 mesi) e una Cost Baseline per il monitoraggio.

## **2. Launching ed Execution (Approccio Agile/Scrum)**
L'esecuzione del progetto è interamente delegata a uno **Scrum Team cross-funzionale e auto-organizzato**, operante in cicli iterativi:
*   **Ruoli Scrum:** Product Owner (priorità di business), Tech Lead (architettura), Scrum Master/PM (processo e ostacoli), Dev Team (implementazione).
*   **Working Agreements e Ritmi:** Il team opera su Sprint di 2 settimane, sincronizzandosi tramite Daily Scrum e validando il lavoro (DoD soddisfatta) nelle Sprint Review con gli stakeholder.
*   **Gestione Incertezza:** Utilizzo di *Spike* tecnici per la validazione precoce delle architetture complesse (es. algoritmo di Machine Learning) e Pair Programming per la mitigazione dei rischi operativi.

## **3. Monitoring, Controlling e Closing (Governance Ibrida)**
Il controllo di progetto fonde metriche tradizionali con unità di misura Agile:
*   **Agile Earned Value Analysis (EVA):** Monitoraggio delle performance di costo (CPI) e schedula (SPI) calcolate sugli Story Points completati rispetto a quelli pianificati, anziché sulle ore spese.
*   **Scope Change Management:** Il cambiamento è accolto ma governato. Nuovi requisiti richiedono un *Agile Swap* (rimozione di User Story di pari peso dal backlog) o l'utilizzo della Time/Budget Contingency.
*   **Issues ed Escalation:** I blocchi operativi vengono risolti dal team (Livello 1). Le deviazioni critiche seguono un protocollo di escalation formale verso il PO (Livello 2) o lo Sponsor (Livello 3).
*   **Post-Implementation Audit:** Il progetto si chiude con una verifica formale dei Success Criteria (es. accuratezza algoritmo >90%, SUS >80) e il Sign-off esecutivo del Product Owner.
