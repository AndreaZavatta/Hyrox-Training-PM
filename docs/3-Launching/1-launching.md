# FASE: LAUNCHING (Esecuzione e Gestione Risorse)

Il progetto "Hyrox Team Performance Optimizer" adotta una fase di Launching (Esecuzione) interamente basata su Scrum, eliminando la rigidità dei tradizionali "Work Packages" a favore di un approccio dinamico gestito tramite Sprint Backlog.

---

## 1. Kick-Off & Regole Operative

Il progetto è stato avviato con un Kick-Off Meeting formale per allineare l'intero Scrum Team (PO, SM, Tech Lead, Dev Team) sulla Product Vision. 
L'esecuzione del lavoro è stata divisa in **Sprints di 2 settimane**. Le regole del team impongono un focus assoluto sulla consegna di software funzionante e sulla risoluzione empirica dei problemi.

---

## 2. Gestione Risorse e Saturazione (Focus Factor)

Il team (5 sviluppatori + SM + PO) è cross-funzionale e auto-organizzato. Per evitare il tipico errore di *over-allocation* (pianificare risorse al 100%), il progetto adotta un **Focus Factor del 75%**:
*   **6 ore/giorno** dedicate allo sviluppo effettivo (WBS/Sprint Backlog).
*   **2 ore/giorno** (25%) riservate all'overhead organizzativo e alle cerimonie (Daily, Review, Code Review).

In caso di colli di bottiglia o problemi su task critici, il team non utilizza tecniche tradizionali di *Resource Leveling*, ma applica lo **Swarming** (collaborazione simultanea di più sviluppatori sulla stessa storia critica) e sfrutta le competenze a "T" per il supporto incrociato. Lo straordinario è un'estrema ratio limitata al max 10%.

---

## 3. Adattamento dello Scope (The Agile Swap)

Il cambiamento dei requisiti durante l'esecuzione è accolto come opportunità, ma gestito tramite regole ferree per proteggere la schedula di 8 mesi:

1.  **Fixed Capacity Trading Rule (Agile Swap):** Qualsiasi nuova User Story urgente che debba entrare nello Sprint corrente o nella Release attuale **deve** essere compensata rimuovendo o posticipando allo *Scope Bank* storie non bloccanti di **pari peso in Story Points**.
    *   *Esempio:* L'anticipazione della funzionalità "Skip & Riordina" (+13 SP) in Release 1 è stata assorbita posticipando cache locale e UI profilo (-14 SP totali).
2.  **Time Contingency:** Il progetto mantiene una riserva temporale del 10% (circa 1.6 Sprint su 16) per assorbire incognite tecniche senza impattare le date di consegna definitive.
