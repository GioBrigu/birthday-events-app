# ROADMAP.md

# Birthday & Events App — Roadmap

La roadmap descrive le fasi principali del progetto.

I dettagli implementativi verranno definiti solo quando si raggiungerà la fase interessata.

## Stato

**Fase corrente:** Fase 0 — Progettazione e requisiti

---

## Fase 0 — Progettazione e requisiti

### Obiettivo

Definire chiaramente cosa deve fare l'MVP e stabilire una base progettuale semplice prima di iniziare l'implementazione.

### Checklist

- [x] Definire obiettivo generale
- [x] Definire stack iniziale
- [x] Definire principi architetturali principali
- [ ] Completare documentazione iniziale
- [ ] Definire i requisiti funzionali dell'MVP
- [ ] Definire il modello concettuale minimo dei dati
- [ ] Definire il primo flusso end-to-end

---

## Fase 1 — Fondamenta applicative e database

### Obiettivo

Creare la struttura minima dell'applicazione e collegarla a PostgreSQL.

### Checklist

- [ ] Struttura iniziale del codice
- [ ] Configurazione applicazione
- [ ] PostgreSQL disponibile in ambiente locale
- [ ] Primo collegamento applicazione-database
- [ ] Modello dati iniziale

---

## Fase 2 — Gestione persone ed eventi

### Obiettivo

Realizzare il nucleo funzionale dell'applicazione.

### Checklist

- [ ] Gestione persone
- [ ] Gestione eventi ricorrenti
- [ ] Persistenza dei dati
- [ ] API necessarie
- [ ] Interfaccia web essenziale
- [ ] Flusso CRUD utilizzabile

---

## Fase 3 — Sistema di notifiche

### Obiettivo

Rendere automatico e affidabile il controllo degli eventi e l'invio dei promemoria.

### Checklist

- [ ] Definire la logica temporale dei promemoria
- [ ] Creare il worker separato
- [ ] Individuare gli eventi da notificare
- [ ] Integrare l'invio email
- [ ] Evitare notifiche duplicate
- [ ] Verificare il flusso end-to-end

---

## Fase 4 — Affidabilità e consolidamento

### Obiettivo

Rendere l'MVP sufficientemente robusto e comprensibile prima di aggiungere nuove funzionalità.

### Checklist

- [ ] Gestione degli errori principali
- [ ] Test delle funzionalità critiche
- [ ] Verifica dei casi limite principali
- [ ] Miglioramento della configurazione locale
- [ ] Revisione della documentazione
- [ ] MVP completato

---

## Fase 5 — Funzionalità AI

### Obiettivo

Integrare l'AI solo dopo che l'applicazione principale funziona correttamente.

### Checklist

- [ ] Definire un caso d'uso AI concreto
- [ ] Integrare un LLM tramite API esterna
- [ ] Generare suggerimenti di messaggi
- [ ] Valutare l'utilizzo delle note sulla persona come contesto
- [ ] Verificare utilità, costi e affidabilità

---

## Fase 6 — Evoluzioni future

### Obiettivo

Valutare eventuali estensioni sulla base dell'esperienza reale con l'MVP.

Possibili evoluzioni verranno aggiunte alla roadmap solo quando emergerà una necessità concreta.

Non fanno parte dell'MVP.