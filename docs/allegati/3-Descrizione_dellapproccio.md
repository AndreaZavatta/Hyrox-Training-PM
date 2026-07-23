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

## **1. Scoping**
La fase di inizializzazione segue un approccio strutturato per garantire l'allineamento degli stakeholder e definire il perimetro del progetto:

* **Definizione del Valore e Requisiti:** Definizione delle **CoS** (Conditions of Satisfaction) per catturare i bisogni del cliente, seguita dalla scomposizione dei requisiti tramite la **RBS (Requirements Breakdown Structure)**, per culminare infine nella redazione del **POS** (Project Overview Statement) che stabilisce obiettivi chiari, criteri di successo e vincoli.
* **Fattibilità e Rischio:** Valutazione della sostenibilità tramite Analisi Finanziaria e identificazione strutturata delle potenziali criticità attraverso l'Analisi dei Rischi.

## **2. Planning**
La pianificazione adotta artefatti flessibili orientati al valore:

* **Gestione dei Requisiti:** I bisogni del cliente sono tradotti in un **Product Backlog** dinamico, stimato in Story Points (SP).
* **Orizzonte Temporale e Regole:** Viene definita una **Release Roadmap** per tracciare la direzione strategica, mentre i **Working Agreements** e il piano di **Governance e Comunicazione** stabiliscono le regole operative del team.

## **3. Launching ed Execution**
Il lavoro è eseguito da uno **Scrum Team cross-funzionale e auto-organizzato** (composto da Product Owner, Tech Lead, Scrum Master/PM e Dev Team), focalizzato sulla consegna incrementale:

* **Kick-off:** La fase di **Launching** si concretizza in un momento di allineamento formale in cui il team si impegna sulle regole definite e sulle baseline (costi/tempi).
* **Ritmo di Sviluppo:** Il team opera in iterazioni (Sprint) brevi, validando il lavoro alla fine di ogni ciclo (Sprint Review) in base alla Definition of Done (DoD).

## **4. Monitoring & Controlling**
Il controllo di avanzamento consolida le metriche tradizionali adattandole all'esecuzione Agile in un unico framework operativo:

* **Agile EVA:** Monitoraggio delle performance di costo (CPI) e schedula (SPI) misurando il valore guadagnato in Story Points rispetto a quelli pianificati.
* **Gestione Cambiamenti ed Escalation:** Il cambiamento è governato tramite meccanismi flessibili (es. *Agile Swap* nel backlog) o l'utilizzo della Contingency. Eventuali ostacoli non risolvibili internamente seguono protocolli di escalation formali verso il PO o il CEO.

## **5. Closing**
La chiusura del progetto è gestita formalmente per massimizzare il valore documentale:

* **Post-Mortem:** Valutazione formale del raggiungimento dei Success Criteria (es. SUS >80, accuratezza algoritmo >90%), raccolta delle *Lessons Learned* e Sign-off esecutivo per lo svincolo delle risorse.
