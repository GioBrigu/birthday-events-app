# DECISIONS.md

# Birthday & Events App — Architecture Decisions

Questo documento registra solamente decisioni già prese.

---

## ADR-001 — Web application

**Stato:** Accettata

### Contesto

L'app deve essere utilizzabile attraverso un'interfaccia semplice e non deve dipendere da un'applicazione desktop specifica.

### Decisione

Il progetto sarà una **web app**.

### Motivazione

Permette di separare interfaccia, logica applicativa e processi automatici mantenendo il progetto accessibile e didatticamente utile.

### Conseguenze principali

- sarà necessario un backend web;
- sarà necessaria un'interfaccia utilizzabile dal browser;
- la logica non dovrà dipendere dal dispositivo client.

---

## ADR-002 — Python + FastAPI

**Stato:** Accettata

### Contesto

Il progetto deve essere coerente con il percorso di apprendimento Python e permettere di lavorare con API e applicazioni backend.

### Decisione

Il backend sarà sviluppato in **Python con FastAPI**.

### Motivazione

Permette di consolidare Python e introdurre in modo pratico API HTTP, JSON, validazione e organizzazione di un'applicazione backend.

### Conseguenze principali

- FastAPI sarà il punto di ingresso web dell'applicazione;
- la struttura del progetto dovrà mantenere separata la logica applicativa dagli endpoint.

---

## ADR-003 — PostgreSQL

**Stato:** Accettata

### Contesto

Persone, eventi e notifiche hanno relazioni e struttura sufficientemente definite.

### Decisione

Il database principale sarà **PostgreSQL**.

### Motivazione

È adatto ai dati relazionali del progetto e permette di esercitare competenze SQL trasferibili ad altri contesti Data Engineering.

### Conseguenze principali

- dovrà essere definito uno schema dati;
- l'applicazione dovrà gestire una connessione a PostgreSQL;
- evoluzioni dello schema dovranno essere gestite in modo controllato.

---

## ADR-004 — Docker per lo sviluppo locale

**Stato:** Accettata

### Contesto

Alcuni componenti dell'applicazione richiedono servizi esterni al processo Python.

### Decisione

**Docker** verrà utilizzato per i servizi necessari allo sviluppo locale.

### Motivazione

Permette di ottenere un ambiente riproducibile senza installare e configurare manualmente ogni servizio sul sistema operativo.

### Conseguenze principali

- almeno PostgreSQL verrà eseguito tramite container;
- la configurazione locale dovrà essere mantenuta semplice e documentata.

---

## ADR-005 — Worker separato dal processo web

**Stato:** Accettata

### Contesto

Le notifiche devono essere controllate e inviate anche senza una richiesta HTTP attiva.

### Decisione

Il controllo degli eventi e l'invio delle notifiche saranno eseguiti da un **worker separato dal processo FastAPI**.

### Motivazione

Il server web e i processi periodici hanno responsabilità differenti e non devono dipendere l'uno dal ciclo di vita dell'altro.

### Conseguenze principali

- esisteranno almeno due processi applicativi distinti;
- web app e worker condivideranno database e logica applicativa dove opportuno;
- dovrà essere definito successivamente come schedulare l'esecuzione del worker.

---

## ADR-006 — Notifiche email

**Stato:** Accettata

### Contesto

L'MVP necessita di un canale di notifica affidabile senza introdurre subito applicazioni mobile o servizi push dedicati.

### Decisione

Il primo canale di notifica sarà **email**.

### Motivazione

È sufficiente per verificare il valore principale dell'app e limita la complessità iniziale.

### Conseguenze principali

- sarà necessario integrare un servizio di invio email;
- dovranno essere gestiti errori di invio e notifiche duplicate;
- altri canali resteranno fuori dall'MVP.

---

## ADR-007 — LLM tramite API esterna

**Stato:** Accettata

### Contesto

Una futura funzionalità potrà generare suggerimenti di messaggi personalizzati.

### Decisione

Le funzionalità LLM utilizzeranno una **API esterna**.

### Motivazione

Non è necessario gestire o eseguire localmente un modello per il caso d'uso previsto.

### Conseguenze principali

- l'AI non sarà necessaria per il funzionamento dell'MVP;
- le credenziali dovranno essere mantenute fuori dal codice;
- dovranno essere considerati costi, privacy e disponibilità del servizio esterno.

---

## ADR-008 — Frontend iniziale semplice

**Stato:** Accettata

### Contesto

Il valore iniziale del progetto dipende dalla logica applicativa e dalle notifiche, non dalla complessità dell'interfaccia.

### Decisione

La prima versione utilizzerà un **frontend semplice**.

### Motivazione

Permette di concentrarsi su Python, API, SQL, database e architettura senza introdurre prematuramente un framework frontend complesso.

### Conseguenze principali

- l'interfaccia dovrà essere funzionale ma essenziale;
- framework frontend complessi non sono una priorità;
- la tecnologia concreta potrà essere scelta quando inizierà la relativa fase.

---

## ADR-009 — Nessun Redis/Celery nella prima versione

**Stato:** Accettata

### Contesto

Un sistema con Redis e Celery potrebbe gestire code e task distribuiti, ma l'MVP ha requisiti molto più limitati.

### Decisione

**Redis e Celery non verranno utilizzati nella prima versione.**

### Motivazione

Introdurrebbero componenti e concetti non necessari per risolvere il problema iniziale.

### Conseguenze principali

- scheduling e worker verranno implementati con una soluzione più semplice;
- l'architettura iniziale avrà meno servizi da configurare e mantenere;
- Redis o sistemi di task queue potranno essere rivalutati solo se emergerà una necessità concreta.