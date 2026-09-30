# PROJECT_BRIEF.md

# Birthday & Events App

## Problema

Compleanni e altri eventi ricorrenti possono essere dimenticati oppure ricordati troppo tardi.

Calendari e promemoria generici permettono di salvare una data, ma questo progetto vuole offrire uno strumento personale focalizzato su:

- persone;
- compleanni;
- eventi ricorrenti;
- notifiche affidabili;
- eventuale supporto AI per preparare un messaggio adatto alla persona.

## Obiettivo principale

Realizzare una web app personale che permetta di registrare persone ed eventi ricorrenti e ricevere automaticamente una notifica email prima dell'evento.

La priorità è costruire prima un'applicazione semplice e affidabile.

Le funzionalità AI verranno aggiunte solo dopo il completamento del flusso principale.

## Utente iniziale

L'utente iniziale è una singola persona che utilizza l'app per gestire i propri compleanni ed eventi ricorrenti.

Non è necessario progettare inizialmente un sistema multiutente.

## MVP

La prima versione utilizzabile deve permettere di:

- creare e gestire persone;
- creare e gestire compleanni ed eventi ricorrenti;
- visualizzare gli eventi registrati;
- salvare i dati in modo persistente;
- individuare gli eventi per cui deve essere inviato un promemoria;
- inviare notifiche email;
- eseguire il controllo delle notifiche in un processo separato dal server web.

## Nice-to-have

Dopo il completamento dell'MVP potranno essere valutate funzionalità come:

- generazione tramite LLM di suggerimenti per messaggi di auguri;
- utilizzo di note sulla persona o sulla relazione come contesto;
- personalizzazione maggiore dei promemoria;
- ricerca più evoluta degli eventi;
- ulteriori funzionalità AI solo se realmente utili.

## Vincoli

Il progetto deve:

- utilizzare strumenti gratuiti o con costi minimi durante lo sviluppo;
- essere eseguibile localmente;
- mantenere l'architettura comprensibile;
- evitare complessità prematura;
- privilegiare affidabilità e chiarezza rispetto al numero di funzionalità;
- avere un consumo di risorse ragionevole;
- essere sviluppato anche come progetto didattico;
- introdurre nuovi strumenti solo quando risolvono un problema reale.

## Stack iniziale

- **Python**
- **uv** per gestione progetto e dipendenze
- **FastAPI** per il backend web/API
- **PostgreSQL** per la persistenza
- **Docker** per i servizi necessari allo sviluppo locale
- **worker separato** per il controllo degli eventi e l'invio delle notifiche
- **email** come primo canale di notifica
- **frontend semplice**, senza framework frontend complessi nella prima versione
- **API LLM esterna** per le future funzionalità AI
- **Git** per il versionamento

Redis e Celery non fanno parte della prima versione.

## Criteri di successo

L'MVP può essere considerato riuscito quando:

1. è possibile registrare una persona e un evento ricorrente;
2. i dati rimangono persistenti tra le esecuzioni dell'applicazione;
3. gli eventi imminenti vengono identificati correttamente;
4. una notifica email viene inviata quando previsto;
5. il sistema di notifiche funziona separatamente dal processo web;
6. il progetto può essere eseguito localmente in modo ripetibile;
7. la struttura del progetto rimane sufficientemente semplice da essere compresa e spiegata;
8. le funzionalità principali sono verificabili prima di introdurre componenti AI.