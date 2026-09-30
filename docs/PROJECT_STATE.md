# PROJECT_STATE.md

# Birthday & Events App — Project State

> Documento operativo. Deve descrivere lo stato attuale del progetto, non la sua storia completa.

## Fase corrente

**Fase 0 — Progettazione e requisiti**

## Obiettivo corrente

Completare la base documentale iniziale e definire con precisione il perimetro dell'MVP prima di iniziare l'implementazione.

## Completato

- [x] Creata cartella `birthday-events-app`
- [x] Inizializzato progetto Python con `uv`
- [x] Creato ambiente virtuale `.venv`
- [x] Inizializzato repository Git
- [x] Creato branch `main`
- [x] Creata cartella `docs/`
- [x] Definito stack architetturale iniziale
- [x] Definito il ruolo del worker separato
- [x] Stabilito che Redis e Celery non saranno usati nella prima versione

## In corso

- [ ] Documentazione iniziale della Fase 0
- [ ] Definizione precisa dei requisiti MVP

## Decisioni già prese

- Web app
- Python + FastAPI
- PostgreSQL
- Docker per lo sviluppo locale
- Worker separato dal processo web
- Email come primo canale di notifica
- LLM tramite API esterna
- Frontend iniziale semplice
- Nessun Redis/Celery nella prima versione

Dettagli e motivazioni sono registrati in `DECISIONS.md`.

## Questioni aperte

- Quali dati minimi deve contenere una persona?
- Quali dati minimi deve contenere un evento?
- Come deve essere configurato l'anticipo della notifica?
- Come gestire correttamente la ricorrenza annuale?
- Quale provider utilizzare per l'invio delle email?
- Quale soluzione utilizzare per eseguire periodicamente il worker?

Le questioni devono essere risolte quando diventano necessarie, senza anticipare decisioni implementative.

## Blocker

**Nessuno.**

## Prossimo passo

Definire i requisiti funzionali dell'MVP e il modello concettuale minimo di **Persona**, **Evento** e **Notifica**.