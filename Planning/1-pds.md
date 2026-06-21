# Project Definition Statement (PDS) / Product Vision & Charter

Il presente **Project Definition Statement (PDS) / Agile Product Vision & Charter** stabilisce gli obiettivi strategici, la governance e la cornice metodologica per lo sviluppo dell'ecosistema "Hyrox Team Performance Optimizer". Questo documento definisce la visione globale del prodotto (Product Vision) e funge da allineamento iniziale tra gli stakeholder e il Scrum Team.

---

## 1. La Squadra di Progetto (Scrum Team)

Il team opera come entità cross-funzionale, auto-organizzata e focalizzata sulla consegna incrementale di valore:

*   **Product Owner (PO):** Detiene la responsabilità esclusiva sul ROI del prodotto, la gestione del Product Backlog, la prioritizzazione delle storie e la validazione dei rilasci.
*   **Scrum Master (SM):** PM / Facilitatore Agile. Responsabile dell'efficacia del team, della rimozione attiva dei blocchi e del rispetto dei principi Scrum.
*   **Dev Team (Developers & Tech Lead):** Responsabili della qualità tecnica, dell'architettura e della stima dello sforzo implementativo in Story Points. Il Tech Lead funge da garante per la coerenza architetturale e detiene il potere di veto sulla fattibilità tecnica dei requisiti.

---

## 2. Il Problema & L'Opportunità di Business

La disciplina atletica Hyrox è caratterizzata da sforzi fisici estremi e transizioni rapide tra corsa e stazioni funzionali di forza. I dispositivi commerciali attuali mostrano forti limiti operativi nel tracciamento multi-esercizio. Ciò costringe:
1.  **Gli atleti:** a interagire manualmente con lo smartwatch durante la gara (spesso con mani bagnate di sudore e battito >180 bpm), aumentando il carico cognitivo e rischiando errori di tracciamento.
2.  **I coach:** a dedicare in media 15 minuti per atleta post-allenamento per correggere e aggregare manualmente i dati (tempi, sanzioni, Roxzone), rendendo il processo non scalabile.
3.  **Il team:** a non disporre di un'analisi in tempo reale del pacing e delle penalità/no-rep accumulate, impedendo decisioni strategiche tempestive.

---

## 3. Product Vision & Goal

Sviluppare un ecosistema software integrato (Wearable watchOS App + Web Dashboard) che sollevi l'atleta dal tracciamento manuale durante la performance e riduca a meno di 2 minuti il tempo di analisi e correzione post-allenamento per il coach, consentendo la pianificazione e l'analisi comparativa delle prestazioni del team.

```
┌──────────────────┐               ┌──────────────────┐
│  Smartwatch App  │ ──(BLE Sync)─►│  Web Dashboard   │
│  (watchOS nativo)│               │  (React/Next.js) │
└──────────────────┘               └──────────────────┘
  - Auto-tracciamento                 - Comparativa split times
  - Feedback aptico                   - Grafici di pacing overlay
  - UI ad alto contrasto              - Gestione sanzioni & ACL
```

---

## 4. Criteri di Successo del Prodotto (Success Criteria)

Il successo del prodotto sarà misurato empiricamente al termine dello sviluppo tramite:
1.  **Efficienza per i Coach:** Tempo medio di editing e analisi post-workout ridotto da 15 minuti a **meno di 2 minuti** nel 95% delle sessioni tracciate.
2.  **Accuratezza dell'Algoritmo:** Discrepanza inferiore al **2%** tra il tempo totale registrato dall'app (incluso di transizioni) e il tempo ufficiale da cronometro manuale di validazione.
3.  **Usabilità Utente:** Punteggio medio di usabilità **SUS (System Usability Scale) >= 80/100** raccolto dai test effettuati sui 15 coach e 30 atleti.

---

## 5. Obiettivi di Prodotto e Sottosistemi

L'architettura del sistema si articola su tre moduli principali, dettagliati nella **Work Breakdown Structure (WBS) / Scomposizione del Backlog** e stimati in Story Points:

### 5.1 Sottosistema Smartwatch (Wearable App)
Applicazione watchOS per Apple Watch 6+ che integra l'algoritmo di classificazione basato sui sensori di movimento (accelerometro/giroscopio) per distinguere automaticamente le stazioni Hyrox dalla corsa. Offre interfacce ad alto contrasto per usabilità sotto stress estremo, note dinamiche del coach e report locale post-attività in modalità *Offline-First*.

### 5.2 Sottosistema Dashboard (Web Portal)
Portale web responsive per il monitoraggio comparativo del team (4 atleti) tramite grafici di pacing e sanzioni in tempo reale. Include il gestore visuale di pianificazione workout (builder) e la gestione dei ruoli con ACL (Coach con permessi completi, Atleta con sola lettura del team e permessi di modifica delle proprie sanzioni).

### 5.3 Sottosistema Sincronizzazione Dati
Protocollo di comunicazione locale Bluetooth tra watch e telefono, con successivo upload automatico su cloud per aggiornare la dashboard del coach. Gestione push per inviare le pianificazioni dal web all'orologio in meno di 10 secondi.

---

## 6. Gestione Agile dei Rischi e Assunzioni

### Assunzioni di Progetto
*   Gli atleti utilizzano Apple Watch Series 6 o superiore con sensori funzionanti.
*   I coach caricano le pianificazioni sulla dashboard prima delle sessioni di allenamento (il tracciamento automatico richiede la struttura del workout pre-caricata).

### Matrice di Valutazione dei Rischi Empirici

| Categoria | Rischio Identificato | P (1-5) | I (1-5) | Score | Strategia di Mitigazione Agile |
| :--- | :--- | :---: | :---: | :---: | :--- |
| **Tecnico** | Errore nel riconoscimento degli esercizi dell'algoritmo (es. Sled Push vs Sled Pull). | 4 | 5 | **20** | Validazione precoce tramite **Spike (Sprint 4)**. Inserimento di un **Gate Go/No-Go nello Sprint 12**: se l'accuratezza è < 90%, pivot immediato sul **Plan B (UI ottimizzata per Fallback Trigger manuale)**. |
| **Ambientale** | Connessione instabile o assente nei capannoni delle palestre. | 3 | 3 | 9 | Architettura **Offline-First** obbligatoria: l'app del watch memorizza localmente in cache e sincronizza in locale appena torna disponibile la rete. |
| **Team** | Abbandono di un membro chiave del team di sviluppo (Bus Factor). | 2 | 4 | 8 | Pratiche di **Pair Programming** sui moduli sensori/sync, documentazione interna su Miro e sessioni settimanali di Knowledge Sharing. |
| **Adozione** | Resistenza dei coach all'uso della nuova dashboard rispetto a fogli Excel. | 2 | 5 | 10 | Coinvolgimento dei 15 coach fin dalle fasi iniziali tramite demo e **Sprint Review periodiche** (ogni 2 settimane). |

---

## 7. Vincoli di Progetto (Constraints)

*   **Hardware di Terze Parti:** Il sistema deve girare esclusivamente sull'hardware Apple Watch esistente (niente sensori esterni o patch proprietarie).
*   **Offline-First:** La mancanza di rete cellulare nelle palestre impone che tutti i flussi di dati continuino a funzionare localmente e si sincronizzino in modo asincrono.
*   **Time-box Fisso:** Il ciclo di rilascio dell'MVP è fissato su **8 mesi (16 Sprint)** con risorse allocate stabili per tutta la durata del progetto.
