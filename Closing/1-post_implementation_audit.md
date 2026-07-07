# Post-Implementation Audit

Il presente documento costituisce l'**audit post-implementazione** del progetto "Hyrox Team Performance Optimizer", condotto al termine dello Sprint 16 (chiusura del ciclo di vita del progetto). L'obiettivo dell'audit è verificare formalmente se il progetto ha raggiunto gli obiettivi definiti nel [POS](file:///home/zava/Projects/PM-project/Scoping/6-pos.md) e nel [PDS](file:///home/zava/Projects/PM-project/Planning/1-pds.md), analizzare gli scostamenti rispetto alla pianificazione e formulare raccomandazioni per i progetti futuri.

---

## 1. Verifica dei Criteri di Successo (Success Criteria)

I criteri di successo del prodotto sono stati definiti nel POS (fase di Scoping) e confermati nel PDS (fase di Planning). Di seguito viene riportata la verifica puntuale di ciascun criterio al termine della fase di Validation (Sprint 12-16).

### 1.1 Tabella di Verifica dei Success Criteria

| # | Criterio di Successo (dal POS) | Target | Risultato Effettivo | Stato | Evidenza |
| :---: | :--- | :---: | :---: | :---: | :--- |
| **SC-1** | Accuratezza dell'algoritmo di riconoscimento automatico delle stazioni | ≥ 90% | **94%** | ✅ Superato | Lab Test con 15 coach e 30 atleti (Sprint 12-13). Misurato su 120 sessioni di allenamento in palestra controllata. |
| **SC-2** | Riduzione del tempo di editing e analisi post-workout per il coach | Da 15 min a < 2 min nel 95% delle sessioni | **1 min 22 sec** (media) nel **97%** delle sessioni | ✅ Superato | Misurato su 85 sessioni tracciate durante la Validation. Le sessioni fuori target (3%) corrispondono a scenari con skip multipli consecutivi (> 3 stazioni riordinate). |
| **SC-3** | Discrepanza tra tempo calcolato dall'app e tempo da cronometro ufficiale | < 2% | **1,3%** | ✅ Superato | Confronto su 40 simulazioni di gara complete (8 stazioni + 8 transizioni). Cronometro ufficiale Hyrox di validazione. |
| **SC-4** | Punteggio SUS (System Usability Scale) | ≥ 80/100 | **83/100** | ✅ Superato | Questionari SUS somministrati a 15 coach e 30 atleti (Sprint 13-14). Punteggio iniziale 74/100, salito a 83/100 dopo le micro-correzioni UI (ISS-008). |

> [!TIP]
> **Tutti e 4 i criteri di successo sono stati soddisfatti.** In particolare, il criterio SC-1 (accuratezza algoritmo) è stato il più critico del progetto e ha richiesto l'attivazione del vincolo di sequenza (ISS-007) per superare il gate Go/No-Go dello Sprint 12. Il Plan B (Manual Trigger) non è stato attivato.

---

## 2. Verifica degli Obiettivi di Progetto (Objectives)

Gli obiettivi di progetto definiti nel POS vengono verificati rispetto ai deliverable effettivamente rilasciati:

| # | Obiettivo (dal POS) | Deliverable Rilasciato | Stato |
| :---: | :--- | :--- | :---: |
| **OBJ-1** | Sviluppo di un'applicazione wearable con algoritmo per il riconoscimento automatico delle stazioni Hyrox | App watchOS rilasciata su App Store con algoritmo di classificazione basato su vincolo di sequenza + dati inerziali (accuratezza 94%) | ✅ Completato |
| **OBJ-2** | Protocollo di sincronizzazione bidirezionale a bassa latenza (Watch ↔ Dashboard tramite smartphone) | Pipeline Bluetooth Watch→Phone + upload Phone→Cloud implementata e validata. Latenza media di push: 6 secondi (target: < 10 sec) | ✅ Completato |
| **OBJ-3** | Web Dashboard multipiattaforma per coach (pianificazione workout + monitoraggio team fino a 4 atleti) | Dashboard React responsive rilasciata con Workout Builder, Template, visualizzazione comparativa, grafici di pacing e gestione sanzioni | ✅ Completato |

---

## 3. Analisi delle Performance di Schedula e Costo

L'analisi di dettaglio è documentata nell'[Earned Value Analysis](file:///home/zava/Projects/PM-project/Monitoring_Controlling/2-earned_value_analysis.md). Di seguito viene riportato il riepilogo finale a chiusura del progetto (Sprint 16).

### 3.1 Riepilogo EVA a Fine Progetto

| Metrica | Valore Pianificato | Valore Effettivo | Variazione |
| :--- | :---: | :---: | :---: |
| **Scope (SP completati)** | 128 SP | 128 SP | 0 SP (100%) |
| **Durata (Sprint)** | 16 Sprint (8 mesi) | 16 Sprint (8 mesi) | 0 Sprint |
| **SPI Finale** | 1,00 | 1,00 | Schedula rispettata |
| **CPI Finale** | 1,00 | 0,99 | Sovracosto dell'1% |

### 3.2 Analisi del Budget

| Voce di Costo | Budget Pianificato | Costo Effettivo | Variazione | Note |
| :--- | :---: | :---: | :---: | :--- |
| **HR (Scrum Team, 8 mesi)** | €232.000 | €234.800 | +€2.800 (+1,2%) | Overtime controllato Sprint 5 (+12h) e overtime marginale Sprint 9-10 |
| **Infrastruttura Cloud (AWS)** | €14.400 | €13.900 | -€500 (-3,5%) | Risorse cloud leggermente sottodimensionate nella fase di Validation |
| **Hardware di Test (Apple Watch)** | Riserva Contingenza | €3.200 | — | 2 Apple Watch aggiuntivi per lo Spike (Sprint 4), coperti dalla Contingency |
| **Strumenti e Licenze** | €6.000 | €5.800 | -€200 | Jira, Confluence, Tempo, Miro, certificati Apple Developer |
| **Riserva di Contingenza** | €24.700 | €3.200 utilizzati | €21.500 non utilizzati | Utilizzata solo per hardware Spike. Il resto è stato restituito al budget aziendale |
| **Totale Progetto** | €277.100 | €257.700 | **-€19.400 (-7,0%)** | Progetto chiuso **sotto budget** grazie al mancato utilizzo della Contingency |

> [!NOTE]
> **Il progetto si chiude sotto budget del 7%.** Il sovracosto operativo dell'1,2% sull'HR è stato ampiamente compensato dal mancato utilizzo della Riserva di Contingenza (€21.500 su €24.700 non consumati). Questo dimostra che la gestione dei rischi tramite Spike e Problem Resolution Meeting ha funzionato in modo efficace, rendendo superfluo l'intervento della riserva nella maggior parte dei casi.

---

## 4. Analisi della Gestione dei Rischi

I rischi identificati nel POS e nel PDS vengono qui valutati retrospettivamente:

| Rischio Identificato | Score (P×I) | Si è Verificato? | Impatto Effettivo | Strategia Applicata |
| :--- | :---: | :---: | :--- | :--- |
| **Errore riconoscimento algoritmo** (Sled Push vs Sled Pull) | 20 | ✅ Sì (ISS-007) | Accuratezza al 88% (sotto soglia) → risolta con vincolo di sequenza → **94% finale** | Spike (Sprint 4), Gate Go/No-Go (Sprint 12), Problem Resolution Meeting straordinario |
| **Connessione instabile in palestra** | 9 | ✅ Sì (parziale) | Nessun impatto operativo: l'architettura Offline-First ha gestito tutti i casi | Architettura Offline-First by-design |
| **Abbandono membro del team** | 8 | ❌ No | — | Pair Programming e Knowledge Sharing hanno mantenuto la ridondanza |
| **Resistenza dei coach all'adozione** | 10 | ❌ No | Il coinvolgimento nelle Sprint Review bisettimanali ha generato buy-in progressivo | Sprint Review con demo live e raccolta feedback diretta |
| **Dati accelerometrici rumorosi** | Non previsto | ✅ Sì (ISS-002) | Rumore ad alta frequenza a velocità > 14 km/h → risolto con filtro di Kalman | Emerso durante lo Spike. Risolto con Problem Resolution Meeting (2h) |
| **Memory leak sessioni lunghe** | Non previsto | ✅ Sì (ISS-004) | Crash app dopo 3,5h → risolto con buffer circolare e batch writing | Livello 1 (Scrum Master-Based). Risolto in 1 Sprint |

> [!IMPORTANT]
> **Lezione appresa sulla gestione dei rischi:** I due rischi più impattanti del progetto (ISS-002 e ISS-007) erano entrambi legati al dominio del riconoscimento automatico. Lo Spike Tecnologico dello Sprint 4 si è rivelato fondamentale: senza i dati raccolti in quella fase, il filtro di Kalman e il vincolo di sequenza non sarebbero stati implementabili in tempo. **La strategia di investire un intero Sprint nella riduzione dell'incertezza tecnica si è dimostrata la decisione più importante del progetto.**

---

## 5. Riepilogo delle Issues e delle Escalation

Il registro completo delle issue (8 totali) mostra un tasso di risoluzione del 100% con un tempo medio di 1,4 Sprint. Solo un'issue ha causato carry-over e nessuna è mai degenerata oltre il Livello 2 di escalation (Scrum Master + PO), confermando un'ottima reattività del team.

---

## 6. Valutazione della Soddisfazione degli Stakeholder

La soddisfazione complessiva è stata valutata molto positivamente:
*   **Product Owner:** Tutti i criteri di business sono stati superati, il prodotto è stato consegnato nei tempi (16 Sprint) e sotto budget del 7%. Visibilità costante garantita dalle Sprint Review.
*   **Utenti Finali (Coach e Atleti):** Punteggio SUS (System Usability Scale) di 83/100. Il tempo di analisi post-workout è sceso da 15 minuti a meno di un minuto e mezzo (media di 1 min 22 sec), con elevato apprezzamento per il feedback aptico e l'efficienza operativa. L'accuratezza del tracciamento si è assestata al 94%.

---

## 7. Accettazione Formale del Progetto

Il Product Owner (Chiara Bertocchi), verificato il raggiungimento del 100% degli Story Points (128/128) e il superamento dei Criteri di Successo e della Definition of Done, dichiara il progetto formalmente accettato e concluso in data 14 Febbraio 2026.---

## 8. Conclusioni dell'Audit

Il progetto "Hyrox Team Performance Optimizer" si chiude con esito **pienamente positivo**:

- **Scope:** 100% completato (128/128 SP). Nessuna User Story eliminata o declassata.
- **Schedula:** Rispettata integralmente (16 Sprint, 8 mesi). SPI finale = 1,00.
- **Budget:** Chiuso sotto budget del 7% (€257.700 su €277.100 pianificati).
- **Qualità:** Tutti e 4 i criteri di successo superati. 8/8 issue risolte. 0 escalation a Livello 3.
- **Rischi:** La strategia di Spike Tecnologico e il gate Go/No-Go si sono dimostrati gli strumenti più efficaci per la mitigazione del rischio tecnico principale.
- **Stakeholder:** Soddisfazione elevata da parte del PO e degli utenti finali (coach e atleti).

Il progetto rappresenta un caso di successo nella gestione di un prodotto software ad alta complessità tecnica (Machine Learning, Sensor Fusion, Bluetooth) mediante una metodologia ibrida (framework Scrum con integrazione controllata degli strumenti di PM tradizionale come EVA, WBS, Work Packages).

---

*Documento redatto dallo Scrum Master Andrea Zavatta al termine dello Sprint 16. L'audit è stato condotto in conformità con le procedure di chiusura definite nella fase di Scoping ([Descrizione dell'Approccio](file:///home/zava/Projects/PM-project/Scoping/3-Descrizione_dellapproccio.md)).*
