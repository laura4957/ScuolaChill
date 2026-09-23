# PRD di ScuolaChill · Team [nome del team]

---

## Informazioni sul documento

|              |                                   |
| ------------ | --------------------------------- |
| **Prodotto** | ScuolaChill                       |
| **Team**     | _nome del team_                   |
| **Autori**   | _nome e cognome di ogni membro_   |
| **Versione** | _1.0_                             |
| **Data**     | _gg/mm/aaaa_                      |
| **Stato**    | _Bozza · In revisione · Validato_ |

### Storico delle versioni

| Versione | Data         | Autore | Cosa è cambiato e perché |
| -------- | ------------ | ------ | ------------------------ |
| 1.0      | _gg/mm/aaaa_ | _nome_ | Prima stesura            |
|          |              |        |                          |

<aside>
💡

Il PRD cambierà durante l'anno. Ogni modifica va registrata qui, con la sua ragione. Un PRD che dice una cosa mentre il codice ne fa un'altra è peggio di nessun PRD.

</aside>

---

# Prima parte · Il cosa

## Scopo e perimetro

### Perché esiste ScuolaChill

**Dal lato business.** _Quale problema risolve, e per chi. Due o tre frasi._

**Dal lato tecnico.** _Cosa copre il sistema, in grandi linee. Due o tre frasi._

### Cosa è incluso

- _Esempio: gestione di classi, docenti e studenti da parte del Direttore_
- _…_

### Cosa non è incluso

- _Esempio: ScuolaChill non gestisce le assenze né le comunicazioni con le famiglie_
- _…_

<aside>
💡

La lista di cosa **non** è incluso è la più preziosa del documento. Ogni riga qui ti evita una settimana di discussioni più avanti.

</aside>

---

## Stakeholder

| Stakeholder                 | Cosa fa                             | Cosa gli interessa | Come lo coinvolgete     |
| --------------------------- | ----------------------------------- | ------------------ | ----------------------- |
| Direttore                   | _…_                                 | _…_                | _…_                     |
| Docenti                     | _…_                                 | _…_                | _…_                     |
| Studenti                    | _…_                                 | _…_                | _…_                     |
| Docente del corso           | Valida il PRD                       | _…_                | Presentazione e domande |
| Collaudatori del primo anno | Usano ScuolaChill come utenti reali | _…_                | _Intervista, collaudo_  |
| _Altri?_                    |                                     |                    |                         |

<aside>
💡

Gli stakeholder non sono solo gli utenti. Sono anche chi approva, chi paga, chi manterrà il sistema. Chiediti chi resterebbe deluso se ScuolaChill non funzionasse.

</aside>

---

## Destinatari e contesto d'uso

### La scuola che avete immaginato

_Descrivi la scuola per cui progettate. Che tipo di istituto è, dove si trova, come si organizza la giornata. Questi dati tornano nella stima del carico, quindi scegli numeri che poi userai davvero._

|                    | Valore                                                          |
| ------------------ | --------------------------------------------------------------- |
| Numero di studenti | _…_                                                             |
| Numero di docenti  | _…_                                                             |
| Numero di classi   | _…_                                                             |
| Orario scolastico  | _es. 8:00 – 14:00, dal lunedì al venerdì_                       |
| Connettività       | _es. Wi-Fi scolastico condiviso, rete mobile degli studenti, …_ |

### Gli archetipi

Arricchisci gli archetipi della traccia.

| ID      | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo principale | Frequenza d'uso |
| ------- | --------- | -------------- | ------------------- | ---------------------- | --------------- |
| ARC-001 | Direttore | _…_            | _…_                 | _…_                    | _…_             |
| ARC-002 | Docente   | _…_            | _…_                 | _…_                    | _…_             |
| ARC-003 | Studente  | _…_            | _…_                 | _…_                    | _…_             |

<aside>
💡

I collaudatori veri sono i ragazzi del primo anno. Usano lo smartphone in corridoio o il PC in laboratorio? La risposta cambia l'interfaccia, i requisiti di usabilità e perfino il dimensionamento.

</aside>

---

## Panoramica e casi d'uso

### ScuolaChill in poche righe

_Racconta ScuolaChill come lo spiegheresti al Direttore in un minuto. Niente termini tecnici._

### User flow e scenari

Per ogni ruolo, scegli **almeno tre** storie principali e descrivi il percorso completo.

**Storia:** _es. STU-02 · Svolgere una verifica_

**User flow**

1. _Lo studente accede a ScuolaChill_
2. _Apre la sezione Verifiche_
3. _…_

**Scenario principale.** _Racconta il caso in cui tutto va bene, con un personaggio e una situazione concreta._

**Scenari alternativi.** _Cosa succede quando qualcosa va storto? Connessione che cade, scadenza superata, doppia scheda aperta…_

_Ripeti il blocco per le storie principali di Direttore e Docente._

---

## Requisiti funzionali

### Le user story della traccia

| ID     | Storia                            | AC aggiunti dal team | Note |
| ------ | --------------------------------- | -------------------- | ---- |
| DIR-01 | Creare account docente            | _…_                  | _…_  |
| DIR-02 | Creare account studente           | _…_                  | _…_  |
| DIR-03 | Creare classi e comporle          | _…_                  | _…_  |
| DIR-04 | Vedere tutto                      | _…_                  | _…_  |
| DOC-01 | Caricare materiale didattico      | _…_                  | _…_  |
| DOC-02 | Creare le proprie verifiche       | _…_                  | _…_  |
| DOC-03 | Assegnare i voti                  | _…_                  | _…_  |
| STU-01 | Consultare il materiale didattico | _…_                  | _…_  |
| STU-02 | Svolgere una verifica             | _…_                  | _…_  |
| STU-03 | Consultare i propri voti          | _…_                  | _…_  |

<aside>
💡

Gli acceptance criteria della traccia sono il minimo. Puoi aggiungerne, non toglierne. Scrivi quelli nuovi nello stesso formato _Dato che / Quando / Allora_.

</aside>

### Le decisioni lasciate aperte dalla traccia

La traccia lascia alcune scelte a te. Ognuna diventa un requisito con il suo ID. Usa questo formato.

> **FR-[AREA]-[NN] · [Titolo]** (collegato a _ID della storia_)
> _Cosa avete deciso, in modo verificabile.Motivazione:_ _perché avete scelto così._

I punti che devi decidere almeno sono questi.

- [ ] La scala dei voti (DOC-03). Da quanto a quanto, con quale passo, se ammette segni come "+" e "−".
- [ ] Il trasferimento di uno studente fra classi (DIR-03). Si può fare? Cosa succede ai voti?
- [ ] La modifica di una verifica dopo lo svolgimento (DOC-02).
- [ ] La connessione che cade durante una verifica (STU-02).
- [ ] Il fallimento del servizio esterno (per esempio l'email delle credenziali).
- [ ] _Altre decisioni che il team ha scoperto_

---

## Requisiti non funzionali

Ogni requisito ha una soglia, una condizione e un modo per verificarlo. Ed è collegato ad almeno una user story.

| ID     | Famiglia      | Requisito                               | Soglia e condizione                                                         | Come si verifica | Storie collegate |
| ------ | ------------- | --------------------------------------- | --------------------------------------------------------------------------- | ---------------- | ---------------- |
| NFR-01 | Prestazioni   | _es. Apertura della verifica nel picco_ | _es. meno di 2 s per il 95% delle richieste, 75 utenti nello stesso minuto_ | _Test di carico_ | _STU-02_         |
| NFR-02 | Sicurezza     | _…_                                     | _…_                                                                         | _…_              | _…_              |
| NFR-03 | Usabilità     | _…_                                     | _…_                                                                         | _…_              | _…_              |
| NFR-04 | Disponibilità | _…_                                     | _…_                                                                         | _…_              | _…_              |
| NFR-05 | Ambientale    | _…_                                     | _…_                                                                         | _…_              | _…_              |
| NFR-06 | Supporto      | _…_                                     | _…_                                                                         | _…_              | _…_              |
| NFR-07 | Interazione   | _…_                                     | _…_                                                                         | _…_              | _…_              |
| NFR-08 | Conformità    | _…_                                     | _…_                                                                         | _…_              | _…_              |

<aside>
💡

Le famiglie da coprire sono queste. **Prestazioni, disponibilità, scalabilità, sicurezza** e **conformità** vengono dalla lezione sui requisiti funzionali e non funzionali. **Usabilità, ambientali, supporto** e **interazione** vengono dalla lezione sul PRD. Se una famiglia resta vuota, scrivi perché non vi riguarda.

I requisiti trasversali della traccia (HTTPS, paginazione, OpenAPI, errori uniformi, Dev e Prod) sono già obbligatori. Riportali qui con il loro ID.

</aside>

### Requisiti impliciti

Prima di chiudere questa sezione, intervista per dieci minuti un ragazzo del primo anno. La domanda è una sola. _"Cosa daresti per scontato che un'app di questo tipo faccia sempre, o non faccia mai?"_

| Chi avete intervistato | Cosa ha detto                     | Requisito che ne avete ricavato |
| ---------------------- | --------------------------------- | ------------------------------- |
| _nome o iniziali_      | _"Il voto non deve sparire, mai"_ | _NFR-…_                         |
|                        |                                   |                                 |

---

## Assunzioni, vincoli e dipendenze

### Assunzioni

Quello che date per vero senza poterlo garantire.

| ID     | Assunzione                                   | Cosa succede se è falsa         |
| ------ | -------------------------------------------- | ------------------------------- |
| ASS-01 | _es. La scuola ha 800 studenti e 60 docenti_ | _Il dimensionamento va rifatto_ |
|        |                                              |                                 |

### Vincoli

I limiti che non potete cambiare.

| ID     | Vincolo                                             | Da dove viene          |
| ------ | --------------------------------------------------- | ---------------------- |
| VIN-01 | _es. Il budget cloud è quello dei crediti studente_ | _Traccia del progetto_ |
|        |                                                     |                        |

### Dipendenze

Le cose esterne senza cui non potete andare avanti.

| ID     | Dipendenza                              | Serve entro          | Chi se ne occupa |
| ------ | --------------------------------------- | -------------------- | ---------------- |
| DIP-01 | _es. Account attivo sul servizio email_ | _Prima del collaudo_ | _nome_           |
|        |                                         |                      |                  |

---

# Seconda parte · Il come

<aside>
💡

Da qui in poi parli al tuo docente e al tuo team, non al Direttore. Ogni scelta tecnica va motivata e confrontata con almeno un'alternativa. "Lo conosciamo" è una motivazione valida, ma non può essere l'unica.

</aside>

## Stima del carico

### Utenti concorrenti

| Situazione                      | Utenti concorrenti | Da dove viene il numero |
| ------------------------------- | ------------------ | ----------------------- |
| Uso normale durante la giornata | _…_                | _…_                     |
| Picco delle 9:00 (verifiche)    | _…_                | _…_                     |
| Fine quadrimestre (voti)        | _…_                | _…_                     |

### Profilo di carico

| Operazione              | Frequente? | Pesante? | Critica? | Note |
| ----------------------- | ---------- | -------- | -------- | ---- |
| Login                   | _…_        | _…_      | _…_      | _…_  |
| Apertura verifica       | _…_        | _…_      | _…_      | _…_  |
| Consegna verifica       | _…_        | _…_      | _…_      | _…_  |
| Dashboard del Direttore | _…_        | _…_      | _…_      | _…_  |
| Caricamento materiale   | _…_        | _…_      | _…_      | _…_  |

<aside>
💡

I numeri di qui devono essere coerenti con la scuola che avete immaginato e con i requisiti non funzionali. Se dichiarate 800 studenti, non potete dimensionare per 20 utenti senza spiegare perché.

</aside>

---

## Scelte tecnologiche

| Area             | Scelta | Alternativa considerata | Perché avete scelto così |
| ---------------- | ------ | ----------------------- | ------------------------ |
| Backend          | _…_    | _…_                     | _…_                      |
| Frontend         | _…_    | _…_                     | _…_                      |
| Database         | _…_    | _…_                     | _…_                      |
| Provider cloud   | _…_    | _…_                     | _…_                      |
| Servizi cloud    | _…_    | _…_                     | _…_                      |
| Regione          | _…_    | _…_                     | _…_                      |
| Servizio esterno | _…_    | _…_                     | _…_                      |

---

## Architettura

### Diagramma dei componenti

_Inserisci qui il diagramma. Deve mostrare i componenti principali e come comunicano._

### I livelli

| Livello                | Cosa fa in ScuolaChill | Esempio concreto |
| ---------------------- | ---------------------- | ---------------- |
| Presentation / API     | _…_                    | _…_              |
| Application / Business | _…_                    | _…_              |
| Data access            | _…_                    | _…_              |

### Le dipendenze fra i livelli

_Chi può conoscere chi, e in quale direzione. Spiega come questa struttura riduce l'accoppiamento e rende il sistema testabile._

---

## Le API

### Le risorse

_Elenca le risorse REST principali. Es. `/classi`, `/verifiche`, `/voti`._

### Il contratto delle API principali

| Verbo    | Route            | Chi può chiamarla | Payload di esempio                | Risposte previste    |
| -------- | ---------------- | ----------------- | --------------------------------- | -------------------- |
| `POST`   | `*/api/docenti*` | _Direttore_       | `*{ "nome": "…", "email": "…" }*` | _201, 400, 403, 409_ |
| `GET`    | _…_              | _…_               | _…_                               | _…_                  |
| `PUT`    | _…_              | _…_               | _…_                               | _…_                  |
| `PATCH`  | _…_              | _…_               | _…_                               | _…_                  |
| `DELETE` | _…_              | _…_               | _…_                               | _…_                  |

### Errori, validazione e paginazione

**Formato uniforme degli errori.** _Mostra un esempio di risposta di errore._

**Validazione degli input.** _Dove avviene e con quali regole._

**Paginazione.** _Come funziona. Parametri, dimensione di default, formato della risposta._

**Documentazione e verifica.** _Come userete OpenAPI/Swagger e la collezione Postman._

---

## Persistenza e modello dei dati

### Diagramma ER

_Inserisci qui il diagramma entità-relazioni con le cardinalità._

### Identificatori

_Come vengono generati gli ID, e perché. Numeri incrementali, UUID, altro?_

### Tre modelli diversi

| Entità     | Nel database | Nel dominio | Esposta dall'API | Dove differiscono e perché |
| ---------- | ------------ | ----------- | ---------------- | -------------------------- |
| _es. Voto_ | _…_          | _…_         | _…_              | _…_                        |

### Normalizzazione e letture aggregate

_Come è normalizzato il modello. Dove serve una lettura denormalizzata, per esempio la pagina dei voti per materia o la dashboard del Direttore._

### Accesso ai dati

_Strategia di accesso ai dati e uso delle query parametrizzate contro la SQL injection._

---

## Sicurezza e integrazione

### Autenticazione e token

_Come si ottiene il token, cosa contiene, come viaggia il profilo utente._

### Chi può fare cosa

| Operazione                    | Direttore | Docente | Studente |
| ----------------------------- | --------- | ------- | -------- |
| Creare un docente             | ✅        | ❌      | ❌       |
| Caricare materiale            | _…_       | _…_     | _…_      |
| Vedere i voti di uno studente | _…_       | _…_     | _…_      |
| _…_                           |           |         |          |

_Spiega dove viene fatto rispettare questo controllo. Ricorda che il frontend non basta mai._

### L'API esterna

_Quale servizio usate, per cosa, e cosa succede quando non risponde._

### Configurazione e segreti

_Dove vivono connection string e segreti, e come cambiano fra Development e Production._

---

## Qualità architetturale

### Organizzazione del codice

_Struttura di progetti, moduli e cartelle, con le motivazioni._

### Dependency inversion e IoC

_Dove li applicate e a cosa servono in ScuolaChill._

### Testabilità

_Cosa testerete, e come separate database e API esterne per sostituirli nei test._

### Development e Production

|          | Development | Production |
| -------- | ----------- | ---------- |
| Database | _…_         | _…_        |
| Segreti  | _…_         | _…_        |
| Log      | _…_         | _…_        |
| _…_      |             |            |

---

## Dimensionamento e costi

| Componente       | Servizio | Taglia (CPU, RAM, storage) | Istanze | Costo mensile stimato |
| ---------------- | -------- | -------------------------- | ------- | --------------------- |
| Backend          | _…_      | _…_                        | _…_     | _…_                   |
| Database         | _…_      | _…_                        | _…_     | _…_                   |
| Storage dei file | _…_      | _…_                        | _…_     | _…_                   |
| _…_              |          |                            |         |                       |
| **Totale**       |          |                            |         | **_…_**               |

**Strategia di scalabilità.** _Verticale o orizzontale? Manuale o automatica?_

**Se la stima si rivela sbagliata.** _Cosa fate se gli utenti sono il doppio? E se sono la metà?_

---

## Piano di deployment

_Come ScuolaChill arriva sul cloud scelto. Come si passa da una versione alla successiva. Come vengono gestite nel tempo le modifiche allo schema del database._

---

# Terza parte · Tempi e valutazione

## Milestone

| Milestone                    | Cosa è pronto    | Data prevista | Responsabile    |
| ---------------------------- | ---------------- | ------------- | --------------- |
| PRD validato                 | Questo documento | _…_           | _tutto il team_ |
| _Prima versione in cloud_    | _…_              | _…_           | _…_             |
| _Collaudo con il primo anno_ | _…_              | _…_           | _…_             |
| _…_                          |                  |               |                 |

<aside>
💡

Stima il tempo di ogni fase come se tutto andasse bene. Poi aggiungi un margine. Non va mai tutto bene.

</aside>

## Piano di valutazione

Come capirete che ScuolaChill funziona e come validerete che la vostra soluzione sta avendo un impatto positivo?

| Metrica                                                    | Obiettivo | Come la misurate                             | Quando       |
| ---------------------------------------------------------- | --------- | -------------------------------------------- | ------------ |
| _es. Collaudatori che completano una verifica senza aiuto_ | _90%_     | _Osservazione durante il collaudo_           | _Collaudo_   |
| _es. Voti persi_                                           | _0_       | _Confronto fra voti inseriti e voti salvati_ | _Primo mese_ |
|                                                            |           |                                              |              |

---

## Acceptance Criteria di questa PRD

- [ ] Ogni parte rappresentata da questo template ha tutte le sezioni richieste senza saltare nessun punto
- [ ] Avete deciso tutti i punti che la traccia e gli esempi lasciano aperti.
- [ ] Ogni requisito non funzionale ha una soglia e una condizione.
- [ ] Ogni NFR è collegato ad almeno una user story.
- [ ] Avete inserito i requisiti impliciti emersi da interviste che avete fatto.
- [ ] Assunzioni, vincoli e dipendenze sono separati e scritti.
- [ ] I numeri della stima del carico sono coerenti con la scuola immaginata e con il dimensionamento.
- [ ] Ogni scelta tecnica ha almeno un'alternativa scartata e una motivazione.
- [ ] La prima parte non contiene scelte tecniche.
- [ ] Lo storico delle versioni è aggiornato .
