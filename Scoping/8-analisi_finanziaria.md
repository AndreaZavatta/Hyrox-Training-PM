**Analisi finanziaria**

**Analisi Costi/Benefici**

**Costi:**

* **Risorse Umane (Fase MVP):** Copre la remunerazione di tutte le figure del team di progetto durante gli 8 mesi di sviluppo: Product Manager (€4.000/mese), Product Owner (€4.000/mese), Tech Lead (€5.000/mese) e i 4 sviluppatori del Core Team (€4.000/mese ciascuno). Il budget mensile per il personale è di €29.000.  
  - €232.000  
* **Attrezzature e Hardware**:  
  Acquisto di diversi modelli di smartwatch (es. Series 6, 7, 8, SE) coerenti con i requisiti di sistema per testare l'algoritmo, validare le performance e mitigare il rischio di "Incompatibilità smartwatch" post-MVP.  
  \- €4.500  
* **Licenze Software e API**:  
  Acquisto di licenze software per gli ambienti di sviluppo, tool di analisi dati e licenze per API.  
  \- €3.000  
* **Riserve di Contingenza:** Il Cost Management prevede l’accantonamento di un budget per gestire l’incertezza.  
  Un fondo dedicato esclusivamente alla gestione dei rischi critici (la PoC che fallisce e l’implementazione del manual trigger).  
  \- €24.700  
* **Costi di Qualità e Validazione:** Costi per organizzare le sessioni di test con atleti reali (affitto spazi, rimborsi, personale di osservazione).  
  \- €2.500  
* **Compliance e Sicurezza:** Costi legali o di consulenza per garantire che i dati biometrici degli atleti siano trattati secondo le normative vigenti  
  \- €5.000

**INVESTIMENTO TOTALE (CapEx): €271.700**

**Benefici:**

**Tangibili:**

* **Aumento dei Ricavi (SaaS Model):** Generazione di flussi di cassa tramite abbonamenti mensili per coach e atleti, giustificati dall'innovazione tecnologica.  
* **Efficienza Operativa per i Coach:** Riduzione del tempo speso nella correzione manuale degli esercizi. Se un coach risparmia il 20% del tempo di monitoraggio, può gestire un numero maggiore di atleti, aumentando la sua produttività.

	**Intangibili:**

* **Miglioramento della Qualità dell'Allenamento:** Avendo dati precisi relativi all’allenamento, il coach può prendere decisioni più precise portando a una riduzione del rischio di infortuni per gli atleti.   
* **Soddisfazione degli Stakeholder:** Allineamento con le aspettative dei coach coinvolti sin dalla fase di scoping, garantendo che il prodotto finale sia adatto allo scopo

**Analisi Breakeven**

Suddividiamo i costi in:

* **Costi fissi (CapEx):** Includono lo sviluppo iniziale, Il Team, l’hardware di test e le consulenze legali (€271.700)  
* **Costi variabili (OpEx):** Includono il mantenimento cloud per team e il supporto tecnico. (€2,50 per team/mese, inclusivo di hosting AWS, database NoSQL per la telemetria e chiamate API)  
* **Prezzo di vendita (abbonamento mensile):** €25 + IVA (22%) per ogni team gestito  
  * Ricavo netto (Senza IVA): €25,00.  
  * Commissioni Store (15%): €3,75.  
  * Ricavo reale per ogni team: €21,25.

* ### **Calcolo del Breakeven Point (BEP)**

  Il Punto di Pareggio indica il numero di "mensilità di abbonamento" ($Q$) necessarie per coprire interamente l'investimento iniziale e i costi di gestione.

  La formula per il calcolo del breakeven point è:
  $$Q = \frac{\text{Costi Fissi (CapEx)}}{\text{Ricavo Reale per Team} - \text{Costo Variabile (OpEx)}}$$

  Sostituendo i valori del progetto:
  $$Q = \frac{271.700 \text{ €}}{21,25 \text{ €} - 2,50 \text{ €}} = \frac{271.700 \text{ €}}{18,75 \text{ €}} \approx 14.490,67 \text{ team totali }$$

**Calcolo del Payback Period (BEP Temporale)** 

*Si assume come dato di partenza l'esito dell'analisi di mercato svolta nel Q1 2026, che stima una conversione minima di 36 coach abbonati entro il primo mese dal rilascio*. 

Il marketing e le vendite rimangono rigorosamente *Out of Scope*. 

Sapendo:

* **Punto di pareggio** (Q): 14.491 abbonamenti totali  
* **Adozione Mensile Stimata:** 540 team attivi al mese (se ogni coach gestisce in media 15 teams, ci servono 36 coach al mese).  
* **Tempo di Recupero (Payback Period):** 14.491 / 540 \= 27 mesi dal rilascio in produzione dell'MVP.

**Return on Investment (ROI)**

Il ROI viene calcolato rapportando l'Utile Netto Cumulato all'Investimento Iniziale (CapEx). Poiché l'investimento di sviluppo (CapEx) è un costo fisso sostenuto interamente nella fase iniziale, mentre i costi di gestione (OpEx) sono ridotti rispetto ai ricavi generati, l'utile netto mensile post-breakeven (€10.125,00/mese) determina una crescita del ROI molto sostenuta all'aumentare dell'orizzonte temporale.

**Dati del Modello (Orizzonte 5 anni)** 

* **Fase di Sviluppo:** 8 mesi (Solo costi: €271.700).  
* **Fase Operativa:** 52 mesi (Ricavi \- Costi variabili).  
* **Base Team media:** 540 abbonamenti team/mese.

**Calcolo dei costi totali**

* **CapEx** (Investimento iniziale fisso): €271.700  
* **OpEx** (Costi variabili 52 mesi): 540 team x 2,50 € x 52 mesi \= €70.200  
* **Costi Totali:** 271.700 \+ 70.200 \= €341.900

**Calcolo dei ricavi totali**

* **Ricavo Netto**: 540 team x 21,25€ x 52 mesi \= €596.700

**Calcolo del ROI Finale (Orizzonte 5 anni)**

**ROI \= (Ricavi Totali - Costi Totali) / CapEx \= (596.700 - 341.900) / 271.700 \= 93,78%**

*Nota di confronto:*
Con lo stesso metodo di calcolo, su un orizzonte di **3 anni** (28 mesi operativi), il ROI sarebbe stato del **4,34%** ($\frac{321.300 - 309.500}{271.700}$), evidenziando come l'estensione del ciclo di vita del software ammortizzi i costi iniziali e incrementi notevolmente la redditività del progetto (un valore che diventa positivo in quanto il tempo di recupero di 27 mesi è ora inferiore al periodo operativo di 28 mesi previsto nel triennio).


## **5. Proiezione del Cash Flow Mensile (Mesi 1-12)**

Per garantire la sostenibilità del progetto e monitorare la liquidità a disposizione a fronte dell'investimento CapEx pianificato di **€247.000** (a cui si somma una riserva di contingency di **€24.700** per un budget totale di **€271.700**), viene presentata la tabella dei flussi di cassa mensili per il primo anno (8 mesi di sviluppo e 4 mesi di commercializzazione).

Le stime considerano:
- **Costo Personale (CapEx)**: €232.000 distribuiti linearmente sugli 8 mesi di sviluppo (€29.000/mese).
- **Infrastruttura, Hardware e Licenze (CapEx)**: €15.000 distribuiti nei mesi 1, 7 e 8 (fase di setup, validazione e compliance).
- **Riserva di Contingenza (CapEx)**: €24.700 tenuti come buffer di cassa e non spesi nel flusso base pianificato.
- **OpEx (Costi di Esercizio Post-Rilascio)**: €2,50/team al mese (hosting server, database telemetria e supporto, escludendo il marketing che è fuori perimetro). L'OpEx varia proporzionalmente al numero di team attivi.
- **Entrate (Inflow)**: Stimate sulla crescita progressiva degli abbonamenti dal mese 9 (Target BEP: 540 team attivi a regime). Si assume un'acquisizione iniziale di 150 team nel Mese 9, che cresce di 100 team al mese fino a 450 team al Mese 12 (ricavo netto: €21,25/team/mese).

| Mese | Attività Principale | Uscite CapEx (€) | Uscite OpEx (€) | Totale Uscite (€) | Entrate Inflow (€) | Flusso Netto Mensile (€) | Cassa Cumulata (€) |
|:---:|:---|:---:|:---:|:---:|:---:|:---:|:---:|
| **M0** | *Investimento Iniziale* | - | - | - | +271.700 | +271.700 | **271.700** |
| **M1** | Setup & Design (WBS 1-3) | 36.500 | - | 36.500 | - | -36.500 | **235.200** |
| **M2** | Sviluppo Inizio (WBS 4-5) | 29.000 | - | 29.000 | - | -29.000 | **206.200** |
| **M3** | Sviluppo (Smartwatch App) | 29.000 | - | 29.000 | - | -29.000 | **177.200** |
| **M4** | Sviluppo (Dashboard/Sync) | 29.000 | - | 29.000 | - | -29.000 | **148.200** |
| **M5** | Sviluppo & Testing (WBS 6-7) | 29.000 | - | 29.000 | - | -29.000 | **119.200** |
| **M6** | Integrazione & QA Testing | 29.000 | - | 29.000 | - | -29.000 | **90.200** |
| **M7** | Beta Test & Validazione | 31.500 | - | 31.500 | - | -31.500 | **58.700** |
| **M8** | Rilascio & Compliance | 34.000 | - | 34.000 | - | -34.000 | **24.700** |
| **M9** | Lancio (150 Team attivi) | - | 375 | 375 | 3.188 | +2.813 | **27.513** |
| **M10** | Esercizio (250 Team attivi) | - | 625 | 625 | 5.312 | +4.687 | **32.200** |
| **M11** | Esercizio (350 Team attivi) | - | 875 | 875 | 7.438 | +6.563 | **38.763** |
| **M12** | Esercizio (450 Team attivi) | - | 1.125 | 1.125 | 9.562 | +8.437 | **47.200** |

*Nota: La riserva di contingency di €24.700 (cassa cumulata al Mese 8) garantisce che il progetto non vada mai in deficit di cassa durante la transizione al regime commerciale.*


  $$ROI = \frac{\text{Ricavi Totali - Costi Totali}}{\text{CapEx}}$$

  Sostituendo i valori del progetto:
  $$ROI = \frac{596.700 \text{ €} - 341.900 \text{ €}}{271.700 \text{ €}} = \frac{254.800 \text{ €}}{271.700 \text{ €}} \approx 93,78\%$$