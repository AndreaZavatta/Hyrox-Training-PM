**RBS: Hyrox Team Performance Optimizer** 

> [!TIP]
> **Miro Link:** La scomposizione visuale di questi requisiti (Requirements Breakdown Structure) è consultabile sulla board: **[Miro Board - CoS & RBS](https://miro.com/app/board/uXjVHGXupJA=/)**.

**Livello 0: Soluzione Integrata per l'Ottimizzazione delle Performance Hyrox Team**

**1\. Requisito: Sistema di Riconoscimento ed Analisi Automatica Esercizi (Smartwatch Atleta)** 

**Business Value:** Eliminazione del carico cognitivo dell'atleta durante lo sforzo estremo, migliorando la focalizzazione sulla performance.

**Rischio:** Limitazioni hardware dei sensori (accelerometro/giroscopio) che potrebbero confondere esercizi simili (es. Sled Push vs Sled Pull).

**1.1 Funzione: Creazione UI per applicazione smartwatch**

* **1.1.1 Sotto-funzione**: Interfaccia rapida per gestione deviazioni workout  
  * **1.1.1.1 Feature**: Capacità di bypassare (skip) la stazione corrente direttamente dall'interfaccia principale dello smartwatch, consentendo la selezione alternativa tra gli esercizi pianificati dal coach. **Flessibilità negli Allenamenti (COULD)**  
  * **1.1.1.2 Feature**: Funzione "Riordina Blocchi" per gestire la sequenza differente dalla schedula degli esercizi **Flessibilità negli Allenamenti (COULD)**  
  * **1.1.1.3 Feature**: Funzionalità di transizione manuale (Fallback Trigger) a basso carico cognitivo per forzare l'avanzamento tra stazioni in caso di mancato riconoscimento o per tracciare esercizi su macchinari non supportati dall'algoritmo. **Affidabilità del dato in Gara (MUST)**

* **1.1.2 Sotto-funzione:** Algoritmo di tracciamento stazioni  
  * **1.1.2.1 Feature:** Funzionalità di identificazione e tracciamento automatico del cambio di stazione Hyrox tramite l'elaborazione dei dati dei sensori di movimento e il confronto con la schedulazione del workout pianificata. **Affidabilità del dato in Gara (MUST)**  
* **1.1.3 Sotto-funzione**: Visualizzazione direttive di allenamento   
  * **1.1.3.1 Feature**: Visualizzazione dinamica a schermo delle note testuali del coach collegate alla stazione Hyrox attiva **Pianificazione workout (MUST)**  
* **1.1.4 Sotto-funzione**: Schermata di riepilogo immediato   
  * **1.1.4.1 Feature:** Generazione automatica di un report locale a fine attività contenente il riassunto dei tempi parziali (split times) per ciascuna delle 8 stazioni e relativi tempi di transizione (Roxzone). **Analisi e Reporting (MUST)**  
* **1.1.5 Sotto-funzione**: Gestione della persistenza dati in modalità offline-first  
  * **1.1.5.1 Feature**: Capacità di memorizzazione locale e continua dei dati biometrici e di movimento in assenza di connettività di rete. **Continuità Operativa (SHOULD)**
* **1.1.6 Sotto-funzione**: Ottimizzazione usabilità sotto sforzo  
  * **1.1.6.1 Feature**: Implementazione di interfacce ad alto contrasto e pulsanti touch di grandi dimensioni, conformi per raggiungere un SUS Score >= 80/100. **Usabilità sotto stress (MUST)**

	

**2\. Requisito: Applicazione Hyrox Team Performance Optimizer (Smartphone/Tablet/PC)**

**Business Value:** Capacità di monitorare l'intero team da un unico dispositivo. Raccolta commenti e pianificazione workout da parte del coach.

**Rischio**: Problemi di scalabilità della UI su schermi di dimensioni diverse. 

**2.1 Funzione: Dashboard per monitoraggio team**

* **2.1.1 Sotto-funzione**: Vista simultanea per team (fino a 4 atleti).  
  * **2.1.1.1 Feature**: Generazione automatica di una tabella comparativa dei tempi parziali (split times) per ogni stazione Hyrox per i 4 atleti, visualizzabile immediatamente dopo la sincronizzazione dei dati. **Analisi e Reporting (MUST)**  
  * **2.1.1.2 Feature**: Visualizzazione di grafici di pacing sovrapposti per identificare discrepanze nelle velocità rispetto ai tempi previsti. **Analisi e Reporting (MUST)**  
  * **2.1.1.3 Feature**: La dashboard deve essere visibile sia dal coach (vista globale team, con possibilità di aggiungere commenti), che dagli atleti (vista filtrata sulle proprie performance, comprensiva della facoltà di inserire e gestire le proprie sanzioni/no-rep, nel rispetto delle regole ACL). **Analisi e Reporting (MUST)**  
* **2.1.2 Sotto-funzione**: Modulo di input diretto per penalità di tempo e no-rep.  
  * **2.1.2.1 Feature**: Gestione sanzioni standard Hyrox di tempo e le no-rep sia da parte del Coach (per l'intero team) sia da parte dell'Atleta (per le proprie sessioni personali). **Analisi e Reporting (MUST)**  
  * **2.1.2.2 Feature**: Registro cronologico delle sanzioni inserite con possibilità di modifica o cancellazione da parte dell'utente autorizzato (Coach o l'Atleta stesso per i suoi dati) prima della generazione del report definitivo. **Analisi e Reporting (MUST)**  
* **2.1.3 Sotto-funzione**: Calcolo e visualizzazione delle analisi di pacing.  
  * **2.1.3.1 Feature**: Visualizzazione comparativa "overlay" tra il tempo totale reale (con sanzioni) e il tempo potenziale "pulito" (senza sanzioni) per valutare l'impatto tecnico sulla performance.  **Analisi e Reporting (MUST)**
* **2.1.4 Sotto-funzione**: Modalità Offline-Cache per la Dashboard  
  * **2.1.4.1 Feature**: Modalità di visualizzazione locale in assenza di rete per consultare un set limitato di dati salvati. **Dashboard Offline-First / Local View (COULD)**

**2.2 Funzione: Dashboard per pianificare workout ad atleti**

* **2.2.1 Sotto-funzione: Modulo di creazione sessioni Hyrox**  
  * **2.2.1.1 Feature:** Interfaccia a blocchi predefiniti per le 8 stazioni ufficiali (es. SkiErg, Sled Push, ecc.), macchinari palestra, oppure corsa (tapis roulant o all’aperto) con campi editabili per peso (kg), distanza (m) o ripetizioni. (Nota: per i macchinari non-Hyrox standard il tracciamento avverrà tramite transizione manuale, in quanto out-of-scope per l'algoritmo automatico). **Pianificazione workout (MUST)**  
* **2.2.2 Sotto-funzione: Gestione libreria allenamenti**  
  * **2.2.2.1 Feature:** Funzione di salvataggio "Template" (es. "Focus Sled Pull" o "Endurance Base") per il riutilizzo rapido in cicli di allenamento diversi.  **Pianificazione workout (MUST)**  
  * **2.2.2.2 Feature:** Possibilità per il coach di allegare brevi note testuali a ogni stazione, visibili sul watch dell'atleta durante l'esecuzione.  **Pianificazione workout (MUST)**

**2.3 Funzione: Gestione Profili Utente e Configurazione Spazio di Lavoro**

* **2.3.1 Sotto-funzione: Modulo di Profilazione e Controllo Accessi (ACL)**   
  * **2.3.1.1 Feature**: Pagina di registrazione e login per accesso immediato dello staff alle dashboard di squadra. **Modulo di Profilazione e Controllo Accessi (ACL) (MUST)**  
  * **2.3.1.2 Feature**: Profilazione differenziata degli utenti con separazione netta dei permessi tra ruolo "Coach" (scrittura e analisi completa del team) e ruolo "Atleta" (lettura dello storico e programmazione, con permessi di scrittura limitati all'inserimento e modifica delle proprie sanzioni personali). **Modulo di Profilazione e Controllo Accessi (ACL) (MUST)**  
* **2.3.2 Sotto-funzione: Configurazione Impostazioni e Preferenze dell'Applicazione**  
  * 2.3.2.1 Feature: Gestione delle impostazioni personali dell'atleta, incluse le soglie cardio personalizzate e la categoria di gara ufficiale di riferimento (Open, Pro, Double, Relay). **Configurazione Impostazioni (MUST)**

**3\. Requisito: Sottosistema per trasferimento workout da watch dell’atleta a dispositivo del coach**

**Business Value:** Risparmio medio di 13 minuti di editing manuale per sessione per ogni atleta.

**Rischio**: Problemi di connettività dei dispositivi o latenza eccessiva in ambienti affollati.

**3.1 Funzione: Sincronizzazione Smartwatch-Smartphone Atleta**

* **3.1.1 Sotto-funzione:** Trasferimento dati dallo smartwatch allo smartphone.
  * **3.1.1.1 Feature:** Capacità del sistema di trasferire l'intera sessione di allenamento dallo smartwatch all'applicazione dello smartphone non appena l'attività viene conclusa dall'atleta. **Analisi e Reporting (MUST)**

  **3.2 Funzione: Sincronizzazione Smartphone Atleta \- Dispositivo Coach** 

* **3.2.1 Sotto-funzione:** Trasferimento dati dallo smartphone dell’atleta al dispositivo del coach.
  * **3.2.1.1 Feature:** Capacità di trasmissione remota dei dati di workout consolidati dallo smartphone dell'atleta verso la dashboard del Coach. **Analisi e Reporting (MUST)**

**3.3 Funzione: Sincronizzazione Workout Push: Dashboard \-> Smartphone \-> Watch**

* **3.3.1 Sotto-funzione:** Trasferimento del piano di allenamento dalla Dashboard allo smartwatch.
  * **3.3.1.1 Feature:** Il sistema deve inviare in modalità push la sequenza strutturata di stazioni verso lo smartwatch dell'atleta entro 10 secondi dalla pubblicazione. **Pianificazione workout (MUST)**

## **Strategia PMLC (iterativo)**

A valle dell'analisi della RBS e delle Condition of Satisfaction, si è deciso che il progetto adotterà un modello PMLC iterativo (scrum) per gestire l’incertezza dell’algoritmo (che è centrale nel raggiungimento degli obiettivi di progetto).




