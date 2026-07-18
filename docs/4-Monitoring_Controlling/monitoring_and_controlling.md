# MONITORING & CONTROLLING

Il monitoraggio del progetto "Hyrox Team Performance Optimizer" segue un approccio Agile snello, mirato a minimizzare l'overhead amministrativo pur mantenendo visibilità su costi, tempi e qualità.

---

## 1. Ritmo dei Meeting (Cerimonie)

Il controllo avviene tramite cicli di feedback rapidi e pre-strutturati:

* **Sprint Planning (max 2 ore - Inizio Sprint):** Controllo "preventivo" a inizio ciclo. Allinea il team sugli obiettivi dello Sprint e definisce il carico di lavoro sostenibile in base alla Velocity storica.
* **Daily Scrum (15 min - Giornaliero):** Sincronizzazione del Dev Team. Aggiorna il Burndown Chart e fa emergere tempestivamente i blocchi. Nessun *problem solving* ammesso durante la riunione.
* **Problem Resolution Meeting (Ad-hoc):** Invocato dallo Scrum Master solo per risolvere gli impedimenti bloccanti emersi durante il Daily.
* **Sprint Review (max 1 ora - Fine Sprint):** Controllo sul *Prodotto*. Si analizzano le metriche (Burndown, Velocity), si dimostra l'incremento agli stakeholder e si concorda l'eventuale aggiornamento dello Scope (Agile Swap).
* **Sprint Retrospective (max 1 ora - Fine Sprint):** Controllo sul *Processo*. Genera action items concreti per migliorare l'efficienza e le dinamiche del team nel ciclo successivo.

---

## 2. Sistema di Reporting e KPI (EVM Agile)

Per evitare inutili documenti testuali lunghi decine di pagine, il progetto si affida a tre strumenti agili e visivi aggiornati dinamicamente su Jira:

1. **Stoplight Report (Semaforo):** Un indicatore visivo (Verde/Giallo/Rosso) condiviso con il PO a fine Sprint, che fotografa istantaneamente la salute di Scope, Schedula, Budget e Qualità.
2. **Velocity & Burndown Chart:** Tracciano il consumo settimanale degli Story Point. La velocity si è mantenuta stabile a una media di 10-13 SP per Sprint.
3. **Earned Value Management (EVM) Semplificato:** Calcolato a livello di Release per validare la salute finanziaria per gli stakeholder tradizionali.
    * **SPI (Schedule Performance Index):** Media progetto **~1.00**. La schedula è stata perfettamente rispettata. L'unico calo (0.98 nello Sprint 5) è stato recuperato immediatamente nello Sprint 6.
    * **CPI (Cost Performance Index):** Media progetto **~0.99**. Un leggerissimo scostamento dovuto a 12h di overtime per i collaudi hardware, ampiamente coperto dalla Contingency Reserve.

---

## 3. Gestione Problemi ed Escalation (Issues Log)

La risoluzione degli imprevisti segue una gerarchia rigida a tre livelli per non fare *micromanagement*:

* **Livello 1 (Scrum Master & Team):** Risoluzione autonoma (es. *swarming* delle risorse). Ha risolto autonomamente il 75% delle issue del progetto.
* **Livello 2 (Negoziazione con PO):** Overtime controllato (max 10%) o *Agile Swap* (sostituzione paritetica dello scope).
* **Livello 3 (Board e Sponsor):** Richiesta di extra-budget o estensione deadline. **Mai attivato** grazie all'efficacia dei Livelli 1 e 2.

### Top 2 Issues Critiche Affrontate (dal Log)
| ID | Sprint | Descrizione del Problema | Azione Risolutiva (Esito) |
| :--- | :---: | :--- | :--- |
| **ISS-003** | S5 | Interferenza hardware tra input fisico dei tasti e i dati dell'accelerometro (rischio ritardo MVP). | **Swarming** rapido di 2 dev nello Sprint 6 per isolare i thread hardware. (*Risolto - Livello 1*) |
| **ISS-007** | S12 | Accuratezza dell'algoritmo ferma all'88% (Target minimo: >90%) nei test di validazione in palestra. | Aggiunta di un **vincolo di sequenza predittiva** nel codice. L'accuratezza è salita al 94%. (*Risolto - Livello 1*) |
