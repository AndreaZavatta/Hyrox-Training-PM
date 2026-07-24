# **Descrizione dell'Approccio Metodologico**

Questo documento sintetizza l'approccio metodologico **Ibrido (Agile/Tradizionale)** adottato per la gestione del progetto "Hyrox Team Performance Optimizer". L'obiettivo è unire la flessibilità esecutiva del framework Scrum con il rigore del Project Management tradizionale, in modo tale da garantire agli stakeholder (es. CEO e investitori) un controllo affidabile sugli obiettivi di alto livello e sui vincoli di budget e di tempo, mantenendo però, a livello esecutivo, l'agilità e la flessibilità tipiche degli Sprint di Scrum.

La scelta di questo approccio è dettata da un vincolo di business critico: **consegnare il software entro 8 mesi esatti**. Questa scadenza è legata alla necessità (imposta dal CEO Giacomo Sirri) di lanciare la piattaforma in corrispondenza del prestigioso evento mondiale Hyrox a Las Vegas previsto al nono mese, lasciando l'ultimo mese libero per la logistica e le campagne di lancio.

## **Water-Scrum-Fall: Il Pattern Ibrido Adottato**

Il progetto adotterà il pattern **Water-Scrum-Fall**, un modello ibrido che combina fasi strutturate sequenziali con sviluppo iterativo:

* **Water (Waterfall) - Fasi Iniziali Predittive:** Le fasi di **Scoping** e **Planning** seguono un approccio tradizionale strutturato. Questo è indispensabile per definire baseline chiare (POS, budget, release roadmap) ed eseguire una rigorosa analisi finanziaria e dei rischi prima dello sviluppo, blindando la schedula di 8 mesi per allinearla alla finestra di lancio.
* **Scrum - Esecuzione Iterativa Adattiva:** La fase di **Launching & Execution** adotterà il framework Scrum puro, con Sprint di 2 settimane, Product Backlog dinamico e consegne incrementali validate empiricamente. Questo garantisce che, entro i vincoli di tempo prefissati, il team sviluppi le funzionalità a maggior valore aggiunto, adattandosi ai riscontri tecnici dei test (es. stabilità dell'algoritmo wearable).
* **Fall (Waterfall) - Chiusura Controllata:** La fase di **Closing** ritornerà a un approccio strutturato per la validazione formale dei Success Criteria (es. SUS e precisione dell'algoritmo), il post-mortem, il sign-off esecutivo e il passaggio formale del software pronto al marketing.

Questo modello consente di **bilanciare prevedibilità e flessibilità**, offrendo al CEO il controllo assoluto sulla data di rilascio strategica (8 mesi) e al Dev Team l'autonomia operativa necessaria per mitigare i rischi tecnici e massimizzare la qualità del codice.

---

## **Le 5 Fasi del PMLC (Project Management Life Cycle)**

Di seguito viene sintetizzato come ciascuna delle 5 fasi del ciclo di vita del progetto sia declinata all'interno dell'approccio ibrido:

* **Scoping:** Definizione del perimetro di progetto e allineamento sulle Conditions of Satisfaction (CoS) tramite la redazione del Project Overview Statement (POS).
* **Planning:** Definizione del Product Backlog prioritizzato in Jira, pianificazione della Release Roadmap (16 Sprint in 8 mesi) e sottoscrizione dei Working Agreements.
* **Launching:** Avvio dello sviluppo operativo in Scrum con un Focus Factor del 75% per prevenire l'over-allocation e gestione dei cambi di perimetro tramite la procedura di Agile Swap.
* **Monitoring & Controlling:** Monitoraggio dell'avanzamento tramite Velocity e Burndown Chart e controllo finanziario e temporale basato su indici EVM (SPI e CPI) riparametrati su Story Points.
* **Closing:** Conduzione del collaudo finale rispetto ai Success Criteria, bilancio finanziario finale e stesura delle Lessons Learned.
