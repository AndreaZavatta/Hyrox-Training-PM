# Earned Value Analysis (EVA)

Il presente documento applica l'analisi dell'Earned Value al progetto "Hyrox Team Performance Optimizer" per misurare le performance di schedula e di costo durante l'esecuzione. L'EVA viene adattata alla metodologia ibrida adottata dal progetto, utilizzando gli **Story Points** come unità di misura del valore e l'**effort in ore/uomo** come unità di misura del costo.

---

## 1. Adattamento dell'EVA al Framework Scrum

In un progetto a metodologia ibrida, l'EVA tradizionale richiede un adattamento metodologico poiché non esistono task con durate fisse e percorsi critici predeterminati per la componente Agile. Il valore viene consegnato in modo incrementale attraverso gli Sprint e misurato tramite Story Points completati.

### 1.1 Definizione delle Metriche nel Contesto Scrum

| Metrica EVA | Definizione Classica | Adattamento Scrum (Progetto Hyrox) |
| :--- | :--- | :--- |
| **BAC** (Budget at Completion) | Costo totale pianificato del progetto | Effort totale pianificato: **5.280 ore/uomo** (5 dev × 8h/giorno × 10gg/Sprint × 11 Sprint di sviluppo + 5 Sprint di validazione) |
| **PV** (Planned Value) | Valore del lavoro pianificato a una certa data | **Story Points cumulativi pianificati** per completamento entro lo Sprint X, secondo la Release Roadmap |
| **EV** (Earned Value) | Valore del lavoro effettivamente completato | **Story Points cumulativi effettivamente completati** (DoD soddisfatta) alla fine dello Sprint X |
| **AC** (Actual Cost) | Costo effettivo del lavoro svolto | **Ore/uomo effettivamente registrate** su Tempo (Jira) fino allo Sprint X, convertite in SP-equivalenti |

### 1.2 Metodo di Misurazione dell'Earned Value

Per la misurazione percentuale del completamento, il team adotta il metodo della **proporzione dei task completati** (il più indicato per Scrum):

$$EV\% = \frac{\text{Story Points Completati (DoD soddisfatta)}}{\text{Story Points Totali Pianificati (BAC)}} \times 100$$

Questo metodo è preferito ai metodi 0-100, 100-0 e 50-50 perché in Scrum ogni User Story completata (con DoD soddisfatta) rappresenta un incremento di valore reale, verificabile e potenzialmente rilasciabile. Non si attribuisce valore parziale alle storie *In Progress* alla fine dello Sprint.

### 1.3 Conversione AC (Ore) in SP-Equivalenti

Per rendere confrontabili PV, EV e AC sulla stessa scala (Story Points), il costo effettivo in ore viene convertito in SP-equivalenti utilizzando il **rapporto di conversione pianificato**:

$$\text{Rapporto di Conversione} = \frac{\text{Ore Pianificate per Sprint (Dev Team)}}{\text{SP Pianificati per Sprint}} $$

*Esempio Sprint 5:* Ore pianificate = 300h, SP pianificati = 13 → Rapporto = 23,1 ore/SP.

---

## 2. Dati di Input: Planned Value (Baseline della Schedula)

La baseline del Planned Value è derivata dalla [Release Roadmap](file:///home/zava/Projects/PM-project/Planning/6-release_roadmap.md) e rappresenta la distribuzione pianificata degli Story Points nei 16 Sprint:

| Sprint | Mese | SP Pianificati | PV Cumulativo (SP) | PV% (su 128 SP) | Fase |
| :---: | :---: | :---: | :---: | :---: | :--- |
| Sprint 1 | M1 | 10 | 10 | 7,8% | Release 1 — Foundation |
| Sprint 2 | M1 | 8 | 18 | 14,1% | Release 1 — Foundation |
| Sprint 3 | M2 | 8 | 26 | 20,3% | Release 1 — Foundation |
| Sprint 4 | M2 | 10 | 36 | 28,1% | Release 1 — Core Wearable |
| Sprint 5 | M3 | 13 | 49 | 38,3% | Release 1 — Core Wearable |
| Sprint 6 | M3 | 13 | 62 | 48,4% | Release 1 — Core Wearable |
| Sprint 7 | M4 | 14 | 76 | 59,4% | Release 1 — Core Wearable |
| Sprint 8 | M4 | 10 | 86 | 67,2% | Release 1 — Sync Pipeline |
| Sprint 9 | M5 | 13 | 99 | 77,3% | Release 2 — Analytics |
| Sprint 10 | M5 | 21 | 120 | 93,8% | Release 2 — Flexibility |
| Sprint 11 | M6 | 8 | 128 | 100,0% | Release 2 — Offline |
| Sprint 12-16 | M7-M8 | 0 | 128 | 100,0% | Release 3 — Validation & Deploy |

> [!NOTE]
> **Sprint 12-16 (Validation):** Questi Sprint non producono nuovi Story Points (non ci sono nuove User Story), ma consumano effort per attività di testing, validazione SUS, system integration e deployment. Nella curva EVA il PV rimane costante a 128 SP, mentre l'AC continua a crescere. Questo è coerente con il modello: il valore del prodotto è stato interamente "guadagnato" entro lo Sprint 11, mentre la fase di validazione rappresenta il costo necessario per portare quel valore alla qualità richiesta per il rilascio.

---

## 3. Tabella EVA Completa: PV, EV, AC, SPI e CPI

Di seguito viene riportata la tabella completa dell'Earned Value Analysis per gli 11 Sprint di sviluppo (Release 1 e Release 2), che rappresentano il periodo in cui il valore del prodotto viene effettivamente generato.

### 3.1 Dati Sprint-by-Sprint

| Sprint | PV (SP) | EV (SP) | AC (SP-eq) | SV (SP) | CV (SP) | SPI | CPI |
| :---: | :---: | :---: | :---: | :---: | :---: | :---: | :---: |
| Sprint 1 | 10 | 10 | 10,0 | 0 | 0 | 1,00 | 1,00 |
| Sprint 2 | 18 | 19 | 18,5 | +1 | +0,5 | 1,06 | 1,03 |
| Sprint 3 | 26 | 27 | 26,5 | +1 | +0,5 | 1,04 | 1,02 |
| Sprint 4 | 36 | 37 | 37,5 | +1 | -0,5 | 1,03 | 0,99 |
| Sprint 5 | 49 | 48 | 51,0 | -1 | -3,0 | 0,98 | 0,94 |
| Sprint 6 | 62 | 63 | 62,0 | +1 | +1,0 | 1,02 | 1,02 |
| Sprint 7 | 76 | 77 | 76,5 | +1 | +0,5 | 1,01 | 1,01 |
| Sprint 8 | 86 | 87 | 86,0 | +1 | +1,0 | 1,01 | 1,01 |
| Sprint 9 | 99 | 99 | 100,0 | 0 | -1,0 | 1,00 | 0,99 |
| Sprint 10 | 120 | 119 | 121,0 | -1 | -2,0 | 0,99 | 0,98 |
| Sprint 11 | 128 | 128 | 129,5 | 0 | -1,5 | 1,00 | 0,99 |

**Legenda delle metriche calcolate:**
*   **SV (Schedule Variance)** = EV - PV → Positivo = in anticipo, Negativo = in ritardo.
*   **CV (Cost Variance)** = EV - AC → Positivo = sotto budget, Negativo = sopra budget.
*   **SPI (Schedule Performance Index)** = EV / PV → >1 = in anticipo, <1 = in ritardo.
*   **CPI (Cost Performance Index)** = EV / AC → >1 = sotto budget, <1 = sopra budget.

### 3.2 Calcolo dell'AC in SP-Equivalenti

L'Actual Cost in SP-equivalenti è stato calcolato convertendo le ore effettivamente registrate su **Tempo (Jira)** per ciascuno Sprint, utilizzando il rapporto di conversione pianificato dello Sprint di riferimento. Il totale delle ore effettive registrate è stato in linea con quelle pianificate, eccetto un lieve overtime nello Sprint 5 (312h su 300h pianificate).

---

## 4. Analisi delle Curve EVA (S-Curve)

### 4.1 Curva PV vs EV vs AC (Sprint 1-11)

**Interpretazione della curva:**
La forma della curva segue il profilo della **Standard S-Curve**: avvio moderato (Sprint 1-3, fase di setup e fondamenta), accelerazione nella fase centrale (Sprint 4-8, sviluppo core wearable) e convergenza finale (Sprint 9-11, analytics e chiusura scope).

Le tre curve (PV, EV, AC) sono sostanzialmente sovrapposte per l'intero arco del progetto, con scostamenti minimi. Questo indica un progetto ben pianificato e controllato.

---

## 5. Analisi degli Indici di Performance (SPI e CPI)

### 5.1 Trend SPI e CPI (Sprint 1-11)

### 5.2 Interpretazione dei Trend

**Schedule Performance Index (SPI):**
*   L'SPI è rimasto costantemente ≥ 0,98 per l'intero progetto, indicando che la schedula è stata sostanzialmente rispettata.
*   Il punto di minimo è stato lo **Sprint 5 (SPI = 0,98)**, dovuto al carry-over di 2 SP della US-W-03 (Fallback Trigger). Lo scostamento è stato immediatamente riassorbito nello Sprint 6 (SPI = 1,02) grazie allo swarming.
*   A fine progetto (Sprint 11), l'SPI è tornato a **1,00**, confermando che tutti i 128 SP sono stati completati nei tempi previsti.

**Cost Performance Index (CPI):**
*   Il CPI ha oscillato tra 0,94 e 1,03, con una media ponderata di **~0,99**.
*   Il punto critico è stato lo **Sprint 5 (CPI = 0,94)**: il team ha consumato 312h effettive contro le 300h pianificate (+12h di overtime controllato), dovute alla complessità della regressione del fallback durante i test post-Spike.
*   Lo **Sprint 4 (CPI = 0,99)** ha registrato un leggero sovracosto legato alle attività di Spike (hardware testing con Apple Watch aggiuntivi), coperto dalla Riserva di Contingenza (€3.200).
*   Il CPI si è stabilizzato attorno a **0,99** dalla Release 2 in poi, indicando un lievissimo sovracosto complessivo dell'1%, ampiamente entro i margini della Riserva di Contingenza.

> [!TIP]
> **Soglia di allarme adottata dal PM:** Il PM monitora i valori SPI e CPI con la seguente regola di escalation:
> - **SPI o CPI ≥ 0,95:** Nessuna azione richiesta (variazione fisiologica).
> - **0,90 ≤ SPI o CPI < 0,95:** Attenzione — analisi delle cause nel Daily e Problem Resolution Meeting.
> - **SPI o CPI < 0,90:** Allarme rosso — attivazione della [Problem Escalation Strategy](file:///home/zava/Projects/PM-project/Monitoring_Controlling/3-issues_log_escalation.md#3-problem-escalation-strategy).
>
> Durante il progetto, **nessuno Sprint ha mai raggiunto la soglia di allarme rosso** (< 0,90).

---



## 7. Riepilogo Esecutivo dell'EVA

| Metrica | Valore a Fine Sprint 11 | Interpretazione |
| :--- | :---: | :--- |
| **BAC** | 128 SP | Scope totale pianificato |
| **EV** | 128 SP | Scope completato al 100% |
| **AC** | 129,5 SP-eq | Sovracosto dell'1,2% (entro margini) |
| **SV** | 0 SP | Perfettamente in schedula |
| **CV** | -1,5 SP | Lieve sovracosto (12h di overtime su 11 Sprint) |
| **SPI** | 1,00 | Schedula rispettata |
| **CPI** | 0,99 | Costi sotto controllo (margine < 1,5%) |

**Conclusione:** L'analisi EVA conferma che il progetto ha completato il 100% dello scope pianificato (128 SP) entro i tempi previsti (Sprint 11), con un sovracosto complessivo trascurabile dell'1,2% rispetto all'effort pianificato. Questo sovracosto è interamente riconducibile all'overtime controllato dello Sprint 5, coperto dal margine del 10% della Time Contingency. Il progetto entra nella fase di Validation (Sprint 12-16) con tutti gli indicatori in zona verde.

---

*Documento redatto dallo Scrum Master Andrea Zavatta. I dati di effort sono estratti da Tempo Timesheets (Jira) e i dati di completamento dal Product Backlog su Jira Board.*
