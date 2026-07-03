# Gestione Operativa dei Cambiamenti (Scope Change Management)

Questo documento illustra l'applicazione pratica del processo di gestione delle modifiche dello scope. Come stabilito nelle politiche di [Change Governance](file:///home/zava/Projects/PM-project/Planning/8-quality_and_change_governance.md#1-gestione-empirica-dei-cambiamenti-scope-control) definite in fase di pianificazione, qualsiasi variazione segue il principio della *Fixed Capacity*. 

Di seguito viene presentata la simulazione del flusso approvativo e della prima **Richiesta di Cambiamento (Scope Change Request - SCR)** operativa del progetto, corredata dal relativo **Project Impact Statement (PIS)**.

---

## 1. Il Processo Operativo di Scope Change

Per garantire il rispetto dei vincoli di budget e di tempo (8 mesi, CapEx di €271.700), l'iter autorizzativo segue la pipeline strutturata descritta di seguito:

```mermaid
graph TD
    A[Rilevazione Necessità o Richiesta del PO] --> B[Compilazione Scope Change Request - SCR]
    B --> C[Analisi dell'Impatto Tecnico e Finanziario - PM/SM]
    C --> D[Redazione del Project Impact Statement - PIS]
    D --> E{Approvazione del Product Owner?}
    E -- NO --> F[Richiesta Respinta / Archiviata]
    E -- SI --> G[Approvazione Cambio Scope & Swap dei Task]
    G --> H[Aggiornamento del Backlog e della Roadmap]
```

### Applicazione della Regola di Scambio (Fixed Capacity Trading Rule)
In base alle linee guida di pianificazione, l'aggiunta di nuove funzionalità nel Backlog deve essere compensata dalla rimozione o posticipazione di elementi di pari sforzo (misurato in Story Points). Questo garantisce che la baseline dei costi e la data di consegna finale non vengano alterate.

---

## 2. Simulazione: Scope Change Request (SCR)

*   **ID Richiesta:** SCR-2026-001  
*   **Data Richiesta:** 10 Febbraio 2026 (Sprint 2)  
*   **Richiedente:** Chiara Bertocchi (Product Owner / Coach)  
*   **Titolo:** Anticipazione della Flessibilità Workout (`US-W-07`) in Release 1.  

### Descrizione della Modifica Richiesta
La Product Owner rileva che durante i test preliminari svolti nei box affiliati, le palestre risultano spesso molto affollate nelle ore di punta. Gli atleti non possono seguire la sequenza lineare e rigida delle 8 stazioni Hyrox senza attendere che i macchinari si liberino. Di conseguenza, la funzionalità di **Skip & Riordina Stazioni (`US-W-07`)**, inizialmente pianificata come *COULD* per la Release 2 (Sprint 10), diventa un fattore critico di adozione (MUST) e deve essere inclusa nella **Release 1 (MVP)** per consentire l'utilizzo reale sul campo.

---

## 3. Project Impact Statement (PIS)

*   **Compilato da:** Andrea Zavatta (Scrum Master / PM)  
*   **Data Analisi:** 12 Febbraio 2026  

### 3.1 Analisi dell'Impatto sullo Sforzo (Story Points)
L'inserimento della storia `US-W-07 (Skip & Riordina Stazioni)` comporta una complessità stimata di **13 Story Points**, a causa della necessità di riscrivere la macchina a stati dello smartwatch per gestire deviazioni dal percorso pianificato e riallineare i dati telemetrici.

### 3.2 Strategia di Mitigazione (The Agile Swap)
Per evitare lo slittamento dei tempi della Release 1 e rispettare la pianificazione finanziaria, lo Scrum Master e Giovanni Manca (Tech Lead) propongono di **scambiare (swap)** la storia richiesta con tre funzionalità non bloccanti della Release 1, posticipandole alla Release 2.

**Storie da Inserire in Release 1:**
*   `US-W-07 (Skip & Riordina Stazioni su Watch)` $\rightarrow$ **+13 Story Points**

**Storie da Posticipare alla Release 2 (Sforzo Equivalente):**
*   `US-W-05 (Caching Locale - Offline-First)` [Parziale] $\rightarrow$ **-8 Story Points** (Si implementa una cache minima di 1 ora anziché 5 ore persistenti su SQLite per l'MVP).
*   `US-D-02 (Profilazione Fisiologica e Gara)` $\rightarrow$ **-3 Story Points** (I parametri cardiaci dell'atleta saranno preimpostati con valori standard di default; il form di profilazione web viene spostato alla Release 2).
*   `US-W-02 (Visualizzazione Note Coach)` $\rightarrow$ **-3 Story Points** (L'atleta non visualizzerà le note testuali del coach sullo schermo del watch in Release 1).

*Bilancio Netto dello Sforzo:* $+13 - 8 - 3 - 3 = \mathbf{-1\ Story\ Point}$ per la Release 1. La schedulazione e il budget dell'MVP sono protetti.

### 3.3 Impatto sui Rischi
L'inserimento del riordino delle stazioni aumenta la complessità del codice dell'applicazione watchOS. Giovanni Manca (Tech Lead) stima un potenziale incremento dei bug logici nella gestione delle transizioni automatiche. 
*   *Mitigazione:* La logica di fallback manuale (`US-W-03`) sarà testata con maggiore frequenza nello Sprint 5 per garantire che l'atleta possa forzare la transizione se il riordino confonde l'algoritmo.

---

## 4. Esito e Firme di Approvazione

La modifica proposta nel Project Impact Statement è stata valutata e approvata dalle parti. La baseline del Product Backlog viene aggiornata di conseguenza.

*   **Approvato da (Product Owner):** *Chiara Bertocchi* (Firma digitale registrata il 14 Feb 2026)  
*   **Approvato da (Scrum Master):** *Andrea Zavatta* (Firma digitale registrata il 14 Feb 2026)
