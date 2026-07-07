# Lessons Learned & Sprint Retrospective Finale

Il presente documento raccoglie le **lezioni apprese** durante l'intero ciclo di vita del progetto "Hyrox Team Performance Optimizer" (16 Sprint, 8 mesi) e riporta gli esiti della **Sprint Retrospective Finale** condotta al termine dello Sprint 16. L'obiettivo è capitalizzare l'esperienza maturata per migliorare i processi nei progetti futuri dell'organizzazione.

---

## 1. Contesto della Retrospettiva Finale

| **Caratteristica** | **Dettaglio** |
| :--- | :--- |
| **Data** | Ultimo giorno dello Sprint 16 (fine Mese 8) |
| **Durata** | 3 ore (retrospettiva estesa rispetto al timebox standard di 90 minuti, trattandosi della chiusura del progetto) |
| **Formato** | In presenza — Team War Room Cesena. Formato "Sailboat Retrospective" (Vento a favore / Ancore / Scogli / Isola del tesoro) |
| **Facilitatore** | Andrea Zavatta (Scrum Master) |
| **Partecipanti** | Intero Scrum Team: Chiara Bertocchi (PO), Giovanni Manca (TL), Luca Rossi, Elena Bianchi, Matteo Neri, Sara Viola |

---

## 2. Lessons Learned — Cosa ha funzionato bene (Vento a favore 🌬️)

### 2.1 Lo Spike Tecnologico come strumento di riduzione dell'incertezza

**Lezione:** Investire un intero Sprint (Sprint 4) nella raccolta dati e nella sperimentazione tecnica, prima di scrivere una singola riga di codice dell'algoritmo di riconoscimento, è stata la decisione più impattante del progetto.

**Evidenza:** Lo Spike ha permesso di:
- Raccogliere 10 dataset inerziali reali che hanno alimentato il filtro di Kalman (ISS-002) e il vincolo di sequenza (ISS-007).
- Identificare precocemente il rumore ad alta frequenza a velocità > 14 km/h, un problema che sarebbe emerso in fase avanzata di sviluppo con costi di correzione molto più alti.
- Fondare il gate Go/No-Go dello Sprint 12 su dati empirici anziché su stime teoriche.

**Raccomandazione per i progetti futuri:** Nei progetti con componenti ad alta incertezza tecnica (Machine Learning, hardware integration, protocolli di comunicazione non standard), pianificare uno **Spike dedicato nel primo terzo del progetto** con budget protetto dalla Riserva di Contingenza. Il costo dello Spike (€3.200 nel nostro caso) è trascurabile rispetto al rischio di scoprire problemi fondamentali in fase di Validation.

---

### 2.2 Il meccanismo di Scope Bank e Agile Swap

**Lezione:** La combinazione della Scope Bank (Time Contingency del 10%) con la regola di Fixed Capacity Trading ha permesso al team di adattarsi ai cambiamenti senza mai compromettere la baseline del progetto.

**Evidenza:**
- L'Agile Swap SWAP-01 (Sprint 2) ha anticipato la US-W-07 (Skip & Riordina) nella Release 1 su richiesta del PO, posticipando 3 User Story di pari valore senza impatto su schedula e budget.
- Il carry-over dello Sprint 5 (-2 SP) è stato assorbito dalla Scope Bank e recuperato nello Sprint 6 tramite swarming (+2 SP).
- A fine progetto, il bilancio netto della Scope Bank è **zero**: ogni prelievo è stato restituito.

**Raccomandazione per i progetti futuri:** La Scope Bank è uno strumento potentissimo nei progetti Scrum con scope semi-fisso (come quelli con deadline e budget definiti). Si raccomanda di **accantonare sempre almeno il 10% della capacità** come buffer e di formalizzare la regola di scambio nel documento di Scope Change Management fin dalla fase di Launching.

---

### 2.3 Il sistema di reporting stratificato

**Lezione:** Differenziare i report per destinatario e livello di dettaglio (Current Period → Cumulative → Variance → Stoplight → Exception) ha eliminato il rischio di information overload per il PO e gli stakeholder, garantendo al contempo piena tracciabilità per il team tecnico.

**Evidenza:**
- Il PO (Chiara Bertocchi) ha dichiarato che lo **Stoplight Report** era l'unico documento che consultava regolarmente, e che la sua chiarezza le ha permesso di fidarsi del team senza dover partecipare ai Daily.
- Il Dev Team ha utilizzato i **Current Period Report** e i **Variance Report** per le analisi interne, senza mai sentirsi "monitorato".
- Nessun **Exception Report** formale è stato necessario durante l'intero progetto.

**Raccomandazione per i progetti futuri:** Adottare sempre un sistema di reporting a più livelli. Il principio guida è: *"Lo stakeholder giusto deve ricevere l'informazione giusta, al livello di dettaglio giusto, al momento giusto."*

---

### 2.4 Swarming come strategia di recupero

**Lezione:** La pratica di convergere più sviluppatori su una singola User Story critica (swarming) si è dimostrata la strategia di recupero più efficace, più rapida e meno costosa dell'overtime.

**Evidenza:**
- ISS-003 (Sprint 5-6): Luca Rossi + Sara Viola hanno completato la US-W-03 in 4 giorni di swarming, recuperando i 2 SP di carry-over.
- ISS-007 (Sprint 12-13): Giovanni Manca + Luca Rossi + Andrea Zavatta in sessione straordinaria da 3 ore hanno ideato e implementato il vincolo di sequenza, portando l'accuratezza dal 88% al 94%.

**Raccomandazione per i progetti futuri:** Lo swarming funziona solo se il team ha competenze cross-funzionali sufficienti. Si raccomanda di mantenere le pratiche di **Pair Programming e Knowledge Sharing** per garantire che almeno 2 membri del team possano lavorare su qualsiasi modulo.

---

## 3. Lessons Learned — Cosa poteva andare meglio (Ancore ⚓)

### 3.1 La stima dell'effort per le User Story di integrazione

**Lezione:** Le User Story che coinvolgono l'integrazione tra sottosistemi diversi (Watch ↔ Phone ↔ Cloud) sono state sistematicamente sottostimate in termini di effort.

**Evidenza:**
- La US-S-03 (Push Workout, Sprint 5) ha richiesto +4h rispetto alla stima a causa della complessità del protocollo push watchOS.
- La US-W-07 (Skip & Riordina, Sprint 10) ha generato ISS-006 per la propagazione inconsistente del flag "Riordinato" alla pipeline di sync.
- Il CPI dello Sprint 5 è sceso a 0,94, il punto più basso dell'intero progetto.

**Causa radice:** Le stime in Planning Poker tendono a sottovalutare la complessità di integrazione perché ogni sviluppatore stima la propria parte senza considerare adeguatamente le interfacce tra i moduli.

**Raccomandazione per i progetti futuri:** Per le User Story che attraversano i confini di sottosistema, applicare un **fattore di complessità aggiuntivo del 20-30%** sulla stima base, oppure spezzare la story in task di integrazione espliciti con owner dedicato.

---

### 3.2 L'usabilità testata troppo tardi

**Lezione:** I test di usabilità SUS sono stati condotti solo allo Sprint 13 (fase di Validation), scoprendo troppo tardi che il punteggio iniziale (74/100) era sotto la soglia di accettazione (80/100).

**Evidenza:**
- ISS-008 ha richiesto micro-correzioni all'UI (aumento font da 24pt a 28pt, feedback aptico) e un ri-test con 10 atleti, che ha occupato parte dello Sprint 14.
- Se il problema fosse stato più grave (es. un redesign completo dell'UI), il progetto avrebbe rischiato un ritardo significativo nella Validation.

**Causa radice:** Il piano di Validation prevedeva i test SUS solo nella fase finale. Non erano stati pianificati test di usabilità intermedi durante lo sviluppo della Release 1 (MVP).

**Raccomandazione per i progetti futuri:** Inserire **test di usabilità leggeri (guerrilla testing)** già dalla Release 1, anche con un campione ridotto (5-8 utenti). Il costo è minimo (1-2 ore per Sprint) e permette di intercettare problemi di UX prima che diventino costosi da correggere.

---

### 3.3 La documentazione tecnica prodotta in ritardo

**Lezione:** La documentazione tecnica (API Swagger, schema DB, guida di architettura) è stata completata quasi interamente negli Sprint 15-16, creando un picco di lavoro nella fase finale del progetto.

**Evidenza:**
- Gli sviluppatori hanno preferito concentrarsi sul codice durante le Release 1 e 2, rimandando la documentazione alla fase di Validation.
- Nello Sprint 15, Matteo Neri ha dedicato il 60% del suo tempo alla stesura della documentazione API anziché al supporto delle attività di deploy.

**Causa radice:** La Definition of Done non includeva esplicitamente la documentazione tecnica come criterio di completamento per le singole User Story.

**Raccomandazione per i progetti futuri:** Integrare la documentazione tecnica nella **Definition of Done** di ogni User Story: *"La User Story non è Done finché l'endpoint API non è documentato su Swagger e lo schema DB è aggiornato."* Questo distribuisce lo sforzo documentale su tutti gli Sprint, evitando il collo di bottiglia finale.

---

## 4. Lessons Learned — Rischi evitati per poco (Scogli 🪨)

### 4.1 Il gate Go/No-Go e il rischio del Plan B

**Lezione:** L'accuratezza dell'algoritmo allo Sprint 12 era al **88%**, sotto la soglia critica del 90%. Se il team non avesse trovato la soluzione del vincolo di sequenza, il progetto avrebbe dovuto attivare il **Pivot al Plan B** (eliminazione del tracciamento automatico), compromettendo il valore differenziante del prodotto.

**Analisi:** Il vincolo di sequenza — far verificare all'algoritmo non "quale stazione è", ma "se il pattern è compatibile con la prossima stazione attesa" — è stata un'idea brillante nata da una sessione di Problem Resolution Meeting di 3 ore. Ma è stata trovata **sotto pressione**, a 4 Sprint dalla fine del progetto.

**Raccomandazione per i progetti futuri:** Anticipare il gate Go/No-Go almeno **2-3 Sprint prima** rispetto alla timeline di fallback. Nel nostro caso, il gate allo Sprint 10 anziché allo Sprint 12 avrebbe dato più margine per iterare sull'algoritmo senza la pressione della deadline di Validation.

### 4.2 Il memory leak nelle sessioni lunghe

**Lezione:** Il memory leak (ISS-004) avrebbe potuto causare crash dell'app durante una gara Hyrox reale (durata fino a 4 ore per i principianti). Il problema è emerso solo durante i test di stress nello Sprint 6, non durante lo sviluppo standard.

**Raccomandazione per i progetti futuri:** Per le applicazioni embedded/wearable con vincoli di risorse hardware (RAM, batteria), pianificare **test di stress fin dal primo Sprint di sviluppo** del modulo interessato, non solo in fase di Validation.

---

## 5. Metriche di Processo — Analisi Retrospettiva

### 5.1 Velocity del Team

| Metrica | Valore |
| :--- | :--- |
| **Velocity media (Sprint 1-11)** | 11,6 SP/Sprint |
| **Velocity massima** | 15 SP (Sprint 6 — swarming post carry-over) |
| **Velocity minima** | 8 SP (Sprint 3 e Sprint 11 — complessità contenuta) |
| **Deviazione standard** | ±2,3 SP |
| **Predictability (SP completati / SP pianificati)** | 100% a fine Sprint 11 (128/128 SP) |

### 5.2 Focus Factor Effettivo

| Metrica | Valore |
| :--- | :--- |
| **Focus Factor pianificato** | 75% |
| **Focus Factor medio effettivo (Sprint 1-11)** | 73,8% |
| **Sprint con FF più basso** | Sprint 5 (72%) — overhead cerimonie Spike + overtime |
| **Sprint con FF più alto** | Sprint 3 (76%) — Sprint stabile senza impedimenti |

> [!NOTE]
> Il Focus Factor effettivo medio (73,8%) è molto vicino al target pianificato (75%), confermando che la stima del 75% è un valore realistico per team Scrum di questa dimensione (5 sviluppatori). Si raccomanda di mantenere questo valore come baseline per i progetti futuri.

### 5.3 Efficacia della Problem Escalation Strategy

| Livello | Issue Gestite | % sul Totale | Tempo Medio di Risoluzione |
| :---: | :---: | :---: | :---: |
| 🟢 Livello 1 (Scrum Master) | 6 | 75% | 1,0 Sprint |
| 🟡 Livello 2 (SM + PO) | 2 | 25% | 2,0 Sprint |
| 🔴 Livello 3 (PO / Sponsor) | 0 | 0% | — |

---

## 6. Piano di Azione per i Progetti Futuri

Sulla base delle lezioni apprese, il team formula le seguenti raccomandazioni operative, ordinate per priorità di impatto:

| # | Raccomandazione | Priorità | Fase di Applicazione |
| :---: | :--- | :---: | :--- |
| **R-01** | Inserire test di usabilità leggeri (guerrilla testing) già dalla Release 1, con cadenza bimestrale | 🔴 Alta | Planning / Launching |
| **R-02** | Anticipare il gate Go/No-Go di 2-3 Sprint rispetto alla deadline di fallback | 🔴 Alta | Planning (Release Roadmap) |
| **R-03** | Applicare un fattore di complessità del +20-30% alle User Story di integrazione cross-sistema | 🟡 Media | Planning (Sprint Planning) |
| **R-04** | Integrare la documentazione tecnica nella Definition of Done di ogni User Story | 🟡 Media | Launching (Working Agreements) |
| **R-05** | Pianificare test di stress per applicazioni embedded/wearable fin dal primo Sprint di sviluppo del modulo | 🟡 Media | Planning (Release Roadmap) |
| **R-06** | Mantenere il Focus Factor al 75% come baseline e lo Spike Tecnologico come pratica standard per progetti ad alta incertezza | 🟢 Bassa | Scoping / Planning |
| **R-07** | Continuare con il sistema di reporting stratificato a 5 livelli e la Scope Bank con Time Contingency del 10% | 🟢 Bassa | Launching / Monitoring |

---

## 7. Ringraziamenti e Chiusura del Team

Lo Scrum Master ringrazia formalmente ogni membro del team per il contributo al successo del progetto:

- **Chiara Bertocchi (PO):** Per la visione chiara del prodotto e la disponibilità costante nelle Sprint Review, che ha garantito un allineamento continuo tra esigenze di business e sviluppo tecnico.
- **Giovanni Manca (TL):** Per la leadership tecnica sull'algoritmo di riconoscimento e l'intuizione del vincolo di sequenza che ha salvato il progetto dal Pivot al Plan B.
- **Luca Rossi:** Per la solidità dello sviluppo wearable e la disponibilità allo swarming nei momenti critici (Sprint 5-6).
- **Elena Bianchi:** Per la qualità della dashboard e le micro-correzioni di usabilità che hanno portato il SUS da 74 a 83/100.
- **Matteo Neri:** Per l'affidabilità dell'infrastruttura backend e la gestione impeccabile del database e delle API.
- **Sara Viola:** Per la meticolosità nei test di integrazione Bluetooth e il contributo determinante alla risoluzione di ISS-003.

Il team viene formalmente **rilasciato** dalle responsabilità di progetto. Le attività di manutenzione evolutiva e supporto post-rilascio saranno gestite da un team operativo dedicato sotto la supervisione del Product Owner.

---

*Documento redatto dallo Scrum Master Andrea Zavatta al termine della Sprint Retrospective Finale (Sprint 16). Le lezioni apprese sono state archiviate nella knowledge base aziendale su Confluence per la consultazione nei progetti futuri.*
