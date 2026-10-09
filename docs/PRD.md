# PRD di ScuolaChill

## Informazioni sul documento

|  |  |
| --- | --- |
| **Prodotto** | ScuolaChill |
| **Team** | Progetto individuale |
| **Autori** | Maria Laura Iacobucci |
| **Versione** | 0.6 |
| **Data** | 09/10/2026 |
| **Stato** | Bozza |

### Storico delle versioni

| Versione | Data | Autore | Cosa è cambiato e perché |
| --- | --- | --- | --- |
| 0.1 | 23/09/2026 | Maria Laura Iacobucci | Prima parte: perimetro e decisioni aperte. |
| 0.2 | 30/09/2026 | Maria Laura Iacobucci | Acceptance criteria aggiunti alle user story. |
| 0.3 | 07/10/2026 | Maria Laura Iacobucci | Seconda parte fino alle scelte tecnologiche, come richiesto. Aggiunte pagina Oggi, griglia delle cattedre e importazione studenti. |
| 0.4 | 08/10/2026 | Maria Laura Iacobucci | Frontend da Angular a React: React lo studio nel corso, Angular non lo padroneggio. Motivato TypeScript, aggiunta la scelta sull'autenticazione e precisati alcuni punti deboli. |
| 0.5 | 09/10/2026 | Maria Laura Iacobucci | Accessibilità (DSA, daltonismo, ipovisione, attenzione) e integrità delle verifiche (ordine casuale di domande e opzioni). |
| 0.6 | 09/10/2026 | Maria Laura Iacobucci | Testi accorciati per una lettura più veloce. Aggiunto il vicario, con gli stessi permessi del direttore. |

---

# Prima parte · Il cosa

## 1. Scopo e perimetro

### 1.1 Perché esiste ScuolaChill

**Dal lato business.** Oggi materiale, verifiche e voti sono sparsi tra chat, email e carta. ScuolaChill li mette in un unico posto: ognuno vede solo ciò che gli spetta e trova subito cosa fare oggi.

**Dal lato tecnico.** Un'applicazione web per telefono e PC. Gestisce account, classi, materiale, verifiche online (anche con Wi-Fi instabile) e voti. Ogni operazione controlla chi la fa e se ne ha il diritto.

### 1.2 Cosa è incluso

- Account di docenti e studenti: creazione (singola o da elenco), modifica, disattivazione.
- Email di attivazione, con lettera stampabile in alternativa.
- Classi, materie, iscrizioni, assegnazione dei docenti e trasferimenti.
- Materiale didattico caricato dai docenti.
- Verifiche a risposta multipla e aperta, svolte online, con ordine di domande e opzioni diverso per ogni studente.
- Verifica seguita in diretta dal docente.
- Voti con commento facoltativo, consultabili per materia.
- Pagina "Oggi" per ogni ruolo.
- Panoramica della scuola e storico delle modifiche per direttore e vicario.
- Recupero della password in autonomia.
- Accessibilità: testo e spaziatura regolabili, temi chiaro, scuro e ad alto contrasto, lettura ad alta voce, misure del PDP applicate da sole, colore mai unico segnale.

### 1.3 Cosa non è incluso

- Assenze, voti orali, pagelle e scrutini: restano sul registro elettronico ufficiale.
- Famiglie, account dei genitori, chat tra utenti.
- Orario, calendario, prenotazione delle aule.
- Iscrizione autonoma: gli account li crea solo la direzione.
- App dagli store e notifiche push: ScuolaChill si usa dal browser.
- Voto deciso dal sistema: il sistema suggerisce, il docente decide.
- Passaggio automatico all'anno successivo.
- Più scuole nello stesso sistema.
- Blocco delle altre schede e controllo con webcam: un sito non può bloccare il dispositivo, e la webcam vorrebbe dire dati biometrici di minorenni.
- Diagnosi e certificazioni: ScuolaChill salva solo le misure del PDP.

### 1.4 Idee per una versione successiva

- Accesso con impronta digitale o volto.
- Notifiche sul telefono.
- Account per i genitori in sola lettura.
- Passaggio d'anno guidato.

---

## 2. Stakeholder

| Stakeholder | Cosa fa | Cosa gli interessa | Come lo coinvolgo |
| --- | --- | --- | --- |
| Direttore e vicario | Gestiscono account e classi, controllano la scuola | Quadro chiaro in pochi minuti, nessun dato perso | Intervista e prova guidata al collaudo |
| Docenti | Materiale, verifiche, voti | Verifiche che non si bloccano, correzione veloce | Intervista e verifica di prova con una classe |
| Studenti | Studiano, svolgono verifiche, guardano i voti | Risposte al sicuro, voti subito, uso da telefono | Collaudo con il primo anno |
| Docente del corso | Valida il PRD | Scelte motivate, sistema che regge | Presentazione e domande |
| Collaudatori del primo anno | Usano ScuolaChill davvero | App chiara e veloce | Intervista e collaudo osservato |
| Referente per l'inclusione | Coordina i PDP | Misure applicate, riservatezza | Revisione delle misure e prova al collaudo |
| Famiglie | Non usano l'app | Dati dei figli protetti | Tramite le regole sulla privacy |
| Responsabile protezione dati | Controlla la liceità del trattamento | Dati minimi, in Europa | Revisione prima dei dati reali |
| Chi manterrà il sistema | Io, poi altri | Codice e documenti chiari | README e PRD aggiornati |

---

## 3. Destinatari e contesto d'uso

### 3.1 La scuola che ho immaginato

Istituto tecnico del nord Italia, lezioni solo di mattina. Le verifiche si fanno spesso alle 9:00, anche in più classi insieme. Gli studenti usano il telefono, i PC sono in laboratorio e condivisi. Il personale ha un'età media alta e poca dimestichezza con strumenti nuovi.

|  | Valore |
| --- | --- |
| Studenti | 590 |
| Docenti | 58 |
| Direzione | 2 account: direttore e vicario |
| Classi | 26, circa 23 studenti ciascuna |
| Materie | 14 |
| Utenti totali | 650 |
| Orario | 8:00 – 14:00, lunedì–venerdì |
| Classi in verifica nello stesso minuto | al massimo 4 |
| Connettività | Wi-Fi condiviso e instabile, rete mobile |
| Dispositivi | Telefoni degli studenti, PC di laboratorio, portatili dei docenti |
| Bisogni specifici | circa 30 studenti con DSA e PDP, circa 24 daltonici |

### 3.2 Gli archetipi

| ID | Archetipo | Contesto d'uso | Competenze digitali | Dispositivo | Frequenza |
| --- | --- | --- | --- | --- | --- |
| ARC-001 | Direttore e vicario | Ufficio, tra una riunione e l'altra | Medio-basse, paura di sbagliare | PC fisso | Molto a settembre, poi 2–3 volte a settimana |
| ARC-002 | Docente | Casa per preparare, classe per le verifiche | Molto variabili | Portatile, a volte telefono | Più volte a settimana |
| ARC-003 | Studente | Corridoio, bus, classe, laboratorio | Alte col telefono, poca pazienza | Telefono, spesso economico | Quasi ogni giorno, pochi minuti |

Il vicario usa ScuolaChill come il direttore e lo sostituisce quando serve: ha lo stesso ruolo e gli stessi permessi (FR-ACC-04).

Quattro persone tipo che l'interfaccia deve servire:

- **Elena, 56 anni, docente di Matematica:** vuole passi guidati e la certezza di non perdere il lavoro.
- **Luca, 31 anni, docente di Informatica:** vuole scorciatoie e fare tutto in fretta.
- **Sara, 14 anni, dislessica:** ha il 30% di tempo in più e la lettura ad alta voce. Non vuole che i compagni lo notino.
- **Tommaso, 15 anni, daltonico:** non distingue il rosso dal verde.

---

## 4. Panoramica e casi d'uso

### 4.1 ScuolaChill in poche righe

ScuolaChill è il posto dove la scuola tiene materiale, verifiche e voti. Lei e il vicario create gli account e decidete chi sta in quale classe e chi insegna cosa. I docenti caricano il materiale e preparano le verifiche, che gli studenti fanno dal telefono anche se il Wi-Fi va e viene. I voti arrivano subito, divisi per materia. Ognuno, appena entra, trova la pagina "Oggi" con le cose da fare. Ognuno vede solo ciò che lo riguarda.

### 4.2 Come è fatta l'esperienza d'uso

L'idea guida: **calma per chi ha paura della tecnologia, veloce per chi ha fretta.** Sette regole:

1. **Si parte da "Oggi":** poche schede, ognuna con un'azione. Esempi: "Verifica di Matematica alle 9:00 · Inizia", "3 consegne da correggere", "Alla 2ªA manca il docente di Inglese".
2. **Un'azione principale per schermata,** con un verbo chiaro: "Consegna", "Salva il voto", "Crea la classe". Icone sempre con una parola.
3. **Passi guidati** per creare classi e verifiche ("Passo 2 di 4"), con bozza salvata da sola.
4. **Scorciatoie per chi va veloce:** ricerca rapida (Ctrl+K), verifiche duplicabili, correzione domanda per domanda.
5. **Leggibilità regolabile** con il pulsante "Aa": testo, spaziatura, temi.
6. **Niente si perde:** salvataggio automatico visibile ("Salvato alle 9:14") e conferma, con la conseguenza scritta, prima di ogni azione irreversibile.
7. **Nessuno resta indietro:** colore mai da solo, pulsante 🔊 per ascoltare, misure del PDP applicate senza doverle chiedere, tutto usabile da tastiera.

**Stile visivo.** Colori pastello con testo scuro e ben contrastato. La mascotte Chilly compare solo nei momenti tranquilli, mai vicino a voti o errori. I voti si leggono come a scuola (6+, 6½, 7−) e quelli insufficienti hanno anche la parola "insufficiente".

**Primo accesso.** Tre schermate di presentazione, saltabili. Ogni pagina ha un "?" con due righe di aiuto.

### 4.3 User flow e scenari

#### Direttore e vicario

##### DIR-02 · Creare account studente

**Flow:** Persone → Studenti → "Aggiungi" o "Importa un elenco" → anteprima con errori evidenziati → conferma → email di attivazione.

**Scenario principale.** A settembre il direttore importa i 120 nuovi iscritti dal file della segreteria. Corregge due righe nell'anteprima e conferma. In 10 minuti tutti hanno un account.

**Scenari alternativi.**

- Campi mancanti o email non valida: i campi sono evidenziati e non si crea niente.
- Email già usata: messaggio chiaro, nessun account creato.
- Servizio email fermo: l'account si crea lo stesso. Il direttore vede "Email non consegnata" con "Reinvia" e "Stampa lettera".
- Link scaduto dopo 72 ore: se ne genera uno nuovo.
- Studente con PDP: il direttore spunta le misure (es. tempo +30%). Nessuna diagnosi.

##### DIR-03 · Creare classi e comporle

**Flow:** Classi → "Crea una classe" → nome → studenti → docenti per materia → riepilogo. La griglia delle cattedre evidenzia le caselle senza docente.

**Scenario principale.** Il vicario crea la 1ªB, aggiunge 23 studenti e assegna i docenti. Inglese resta vuota e la griglia la segnala.

**Scenari alternativi.**

- Studente già in un'altra classe: si propone "Trasferisci".
- Trasferimento: i vecchi voti restano, cambia il materiale visibile.
- Studente con verifica in corso: trasferimento bloccato fino alla consegna.
- Docente già assegnato a quella materia: rifiutato.
- Classe con studenti: non si può eliminare.

##### DIR-04 · Vedere tutto

**Flow:** Panoramica → numeri principali → classi, docenti, andamento dei voti → dettaglio → storico.

**Scenario principale.** Prima del collegio docenti il direttore nota che la 1ªC va male in Matematica e ne parla con la docente, senza chiedere dati a nessuno.

**Scenari alternativi.**

- Un docente prova ad aprire la Panoramica: accesso negato.
- Dati con qualche minuto di ritardo: si vede l'ora dell'ultimo aggiornamento.
- Classe senza voti: "Ancora nessun voto", non zero.

#### Docente

##### DOC-01 · Caricare materiale didattico

**Flow:** classe e materia → "Carica materiale" → file o link → titolo → pubblicato dopo il controllo di sicurezza.

**Scenario principale.** Elena carica un PDF di esercizi in 1ªB e 1ªC. Giulia lo trova in "Oggi" il mattino dopo.

**Scenari alternativi.**

- File troppo grande o con macro: rifiutato con spiegazione.
- Classe non sua: negato.
- Materiale di un collega: non può modificarlo né eliminarlo.
- File rifiutato dal controllo: gli studenti non lo vedono mai.
- PDF scansionato: avviso che non si può ascoltare né ingrandire bene.

##### DOC-02 · Creare le proprie verifiche

**Flow:** "Nuova verifica" → titolo e orari → domande (ordine casuale già attivo) → anteprima → bozza o programmata. Si apre e si chiude da sola.

**Scenario principale.** Elena prepara 10 domande per giovedì alle 9:00, la rilegge il giorno dopo e la programma. Luca duplica la sua su tre classi.

**Scenari alternativi.**

- Errore scoperto a verifica aperta: si può solo prolungare o annullare con un motivo.
- Verifica con consegne: si può solo annullare, non eliminare.
- Verifica di un collega: modifica negata.

##### DOC-03 · Assegnare i voti

**Flow:** "Segui la verifica" in diretta → dopo la chiusura, elenco consegne → punteggio suggerito per le crocette → voto e commento.

**Scenario principale.** Durante la verifica Elena vede che Marco è offline e lo rassicura. Il giorno dopo corregge domanda per domanda e dà a Giulia 7½ con un commento.

**Scenari alternativi.**

- Voto fuori scala (6,3 o 11): non salvato, con i valori ammessi.
- Correzione di un voto: serve un motivo, resta nello storico.
- Studente che non ha consegnato: nessun voto possibile.
- Verifica di un collega: negato anche con chiamata diretta.

#### Studente

##### STU-01 · Consultare il materiale didattico

**Flow:** materie della classe → materia → materiale dal più recente → apri o scarica.

**Scenario principale.** Marco, la sera prima della verifica, scarica gli esercizi dal telefono.

**Scenari alternativi.**

- Link a materiale di un'altra classe: negato.
- Materia senza materiale: messaggio chiaro, non una pagina vuota.

##### STU-02 · Svolgere una verifica

**Flow:** "Oggi" → "Inizia" → risposte salvate mentre scrive → "Consegna" con riepilogo → conferma.

**Scenario principale.** Alle 9:00 Giulia apre la verifica insieme ad altre tre classi, risponde e consegna alle 9:42.

**Scenari alternativi.**

- Cade il Wi-Fi: "Sei offline. Le tue risposte sono al sicuro." Al ritorno si sincronizza tutto.
- Telefono scarico: riprende dal PC lo stesso tentativo.
- Tempo scaduto: conta l'orologio del server, 60 secondi di tolleranza, poi consegna automatica.
- Verifica già consegnata o di un'altra classe: negato.
- Due schede aperte: stesso tentativo, una sola consegna.
- Marco sente "la terza è la B": per lui la terza domanda è un'altra.
- Sara ha il tempo +30%: il suo contatore parte da 65 minuti invece di 50, senza chiedere niente.
- Tommaso è daltonico: ogni stato ha icona e parola, non solo colore.

##### STU-03 · Consultare i propri voti

**Flow:** Voti → una scheda per materia con media e voti → andamento → "Quanto mi serve?".

**Scenario principale.** Giulia trova il 7½ con il commento della docente e scopre che con un 8 arriverebbe al 7 di media.

**Scenari alternativi.**

- Voti di un compagno: negato.
- Studente trasferito: vede anche i voti della classe precedente.
- Voto corretto: vede quello aggiornato.

---

## 5. Requisiti funzionali

### 5.1 Le user story della traccia

Gli acceptance criteria della traccia restano tutti validi. Qui ci sono quelli aggiunti. Dove la storia dice "Direttore", vale anche per il vicario (FR-ACC-04).

| ID | Storia | AC aggiunti | Note |
| --- | --- | --- | --- |
| DIR-01 | Creare account docente | AC-04 · Dato che creo un docente, Quando va a buon fine, Allora riceve un link di attivazione valido 72 ore e nessuna password per email.<br>AC-05 · Dato che l'email non è consegnata, Quando apro l'elenco, Allora vedo "non consegnata" e posso reinviarla o stampare un codice. | FR-INT-01, FR-ACC-01 |
| DIR-02 | Creare account studente | AC-04 · Dato che creo uno studente, Quando va a buon fine, Allora riceve un link di attivazione valido 72 ore.<br>AC-05 · Dato che disattivo uno studente, Quando prova ad accedere, Allora è negato ma i voti restano. | FR-INT-01, FR-ACC-01, FR-ACC-02 |
| DIR-03 | Creare classi e comporle | AC-04 · Dato che trasferisco uno studente, Quando confermo, Allora la vecchia iscrizione si chiude, i voti restano e vede solo il materiale della nuova classe.<br>AC-05 · Dato che ha una verifica in corso, Quando provo a trasferirlo, Allora è impedito fino alla consegna.<br>AC-06 · Dato che un docente è già assegnato per quella materia, Quando lo riassegno, Allora ricevo un errore. | FR-CLA-01, FR-ASS-01 |
| DIR-04 | Vedere tutto | AC-04 · Dato che apro la panoramica, Quando si carica, Allora vedo l'ora dell'ultimo aggiornamento.<br>AC-05 · Dato che apro una classe con voti, Quando la guardo, Allora vedo la media per materia. | Include lo storico delle modifiche |
| DOC-01 | Caricare materiale didattico | AC-04 · Dato che carico un file non ammesso o oltre 25 MB, Quando confermo, Allora ricevo un errore con formati e limite.<br>AC-05 · Dato che il controllo di sicurezza non è concluso o ha rifiutato il file, Quando gli studenti aprono la materia, Allora non lo vedono. | FR-MAT-01 |
| DOC-02 | Creare le proprie verifiche | AC-04 · Dato che la verifica è aperta, Quando modifico le domande, Allora è negato; posso solo prolungare o annullare con un motivo.<br>AC-05 · Dato che ha almeno una consegna, Quando provo a eliminarla, Allora posso solo annullarla. | FR-VER-01, FR-VER-03, FR-VER-05 |
| DOC-03 | Assegnare i voti | AC-04 · Dato che correggo un voto, Quando confermo, Allora serve un motivo e resta nello storico.<br>AC-05 · Dato che lo studente non ha consegnato, Quando provo a dargli un voto, Allora è negato. | FR-VOT-01, FR-VOT-02 |
| STU-01 | Consultare il materiale didattico | AC-03 · Dato che sono stato trasferito, Quando cerco il materiale della vecchia classe, Allora non lo vedo.<br>AC-04 · Dato che i materiali sono molti, Quando apro la materia, Allora sono paginati, dal più recente. | FR-CLA-01, FR-MAT-01 |
| STU-02 | Svolgere una verifica | AC-04 · Dato che perdo la connessione, Quando torno online prima della fine, Allora ritrovo tutte le risposte.<br>AC-05 · Dato che il tempo scade, Quando non ho consegnato, Allora la verifica si consegna da sola.<br>AC-06 · Dato che cambio dispositivo, Quando riprendo, Allora continuo lo stesso tentativo. | FR-VER-02, FR-INC-01 |
| STU-03 | Consultare i propri voti | AC-03 · Dato che un voto viene corretto, Quando apro i voti, Allora vedo quello aggiornato.<br>AC-04 · Dato che ho voti con +, ½ o −, Quando li guardo, Allora li vedo come 6+, 6½, 7−. | FR-VOT-01 |

### 5.2 Le decisioni lasciate aperte dalla traccia

> **FR-VOT-01 · Scala dei voti** (DOC-03, STU-03)
> Da 1 a 10, a passi di 0,25. Si legge come a scuola: 6,25 = "6+", 6,5 = "6½", 6,75 = "7−". Altri valori rifiutati.
> _Perché:_ è come votano i docenti, e un numero permette medie esatte.
> _Scartato:_ "6+" salvato come testo (niente medie); scala 0–100.

> **FR-CLA-01 · Trasferimento fra classi** (DIR-03, STU-01, STU-03)
> Solo direttore e vicario, con l'azione "Trasferisci". La vecchia iscrizione si chiude, se ne apre una nuova. I voti restano legati a verifica, classe e docente originali. Bloccato se c'è una verifica in corso.
> _Perché:_ lo storico non si riscrive.
> _Scartato:_ vietare i trasferimenti; spostare i vecchi voti nella nuova classe.

> **FR-VER-01 · Ciclo di vita della verifica** (DOC-02)
> Bozza → Programmata → Aperta → Chiusa → Valutata, oppure Annullata.
>
> - Bozza e Programmata: tutto modificabile.
> - Da Aperta: contenuto bloccato, solo proroga o annullamento con motivo.
> - Con consegne: solo annullabile.
> - Voti correggibili sempre, con motivo e storico.
>
> _Perché:_ cambiare le domande a verifica iniziata è ingiusto.
> _Scartato:_ modifica libera; blocco totale senza correzioni.

> **FR-VER-02 · Connessione che cade** (STU-02)
>
> - Ogni risposta si salva mentre si scrive, con copia sul dispositivo.
> - Offline: avviso tranquillo, sincronizzazione automatica al ritorno.
> - Si può riprendere da un altro dispositivo.
> - Conta l'orologio del server: 60 secondi di tolleranza, poi consegna automatica. Il docente può concedere una proroga.
>
> _Perché:_ il Wi-Fi che cade è la normalità.
> _Scartato:_ salvare solo alla consegna.

> **FR-INT-01 · Servizio email fermo** (DIR-01, DIR-02)
> L'account si crea sempre. L'email va in coda e il sistema riprova 5 volte in circa 8 ore. Poi la direzione vede "non consegnata" con "Reinvia" e "Stampa lettera" (con codice monouso).
> _Perché:_ un servizio esterno non deve bloccare la scuola.
> _Scartato:_ annullare la creazione se l'email fallisce.

### 5.3 Altre decisioni

> **FR-ACC-01 · Disattivazione** (DIR-01, DIR-02)
> Durante l'anno gli account si disattivano, non si cancellano: voti e contenuti restano. Gli studenti che lasciano la scuola vengono cancellati dopo 12 mesi, salvo diversa indicazione.
> _Perché:_ un clic sbagliato non deve cancellare un anno di voti.

> **FR-ACC-02 · Password dimenticata** (DIR-01, DIR-02)
> Reset da soli con un link via email; in alternativa nuova lettera di attivazione. Nessuna password mai in chiaro.
> _Perché:_ la direzione non deve fare da help desk.

> **FR-ACC-03 · Secondo fattore per il personale** (DIR-01, DOC-03)
> Direttore, vicario e docenti confermano l'accesso con un codice a sei cifre da un'app o, in alternativa, via email. Possono ricordare il proprio dispositivo per 30 giorni.
> _Perché:_ chi può cambiare i voti non deve dipendere da una sola password. Le alternative lo rendono sopportabile per tutti.

> **FR-ACC-04 · Il vicario** (DIR-01…DIR-04)
> Il vicario ha lo stesso ruolo e gli stessi permessi del direttore. Nello storico ogni azione riporta chi l'ha fatta, quindi si distingue sempre tra i due.
> _Perché:_ il vicario sostituisce il direttore quando è assente, e la scuola non deve fermarsi.
> _Scartato:_ un ruolo separato con permessi ridotti, che complicherebbe tutto senza un vantaggio reale.

> **FR-ASS-01 · Docente sostituito** (DIR-03, DOC-01, DOC-02)
> L'assegnazione si chiude, materiale e verifiche restano visibili. La direzione può passarne la proprietà al nuovo docente.
> _Perché:_ niente contenuti orfani, e la regola "solo se è mio" resta valida.

> **FR-ASS-02 · Un docente per materia per classe** (DIR-03, STU-01)
> Al massimo un docente attivo per materia in ogni classe.
> _Perché:_ lo studente deve sapere chi è il docente di quella materia.

> **FR-VOT-02 · Assenti e voti orali** (DOC-03)
> Voto solo per verifiche consegnate. Assenze e orali sono fuori perimetro.

> **FR-VER-03 · Tipi di domanda** (DOC-02, DOC-03, STU-02)
> Risposta multipla (una giusta) e aperta. Il sistema suggerisce il punteggio, il docente decide.
> _Perché:_ perimetro gestibile da sola.

> **FR-VER-04 · Domande segrete fino all'apertura** (DOC-02, STU-02)
> Prima dell'inizio lo studente vede solo titolo, data e durata. Le risposte corrette non arrivano mai sul suo dispositivo.
> _Perché:_ altrimenti basterebbe guardare dentro la pagina.

> **FR-VER-05 · Integrità della verifica** (DOC-02, DOC-03, STU-02)
> Ordine di domande e opzioni diverso per ogni studente: attivo di base, disattivabile. L'ordine resta lo stesso se lo studente cambia dispositivo. Il docente corregge sempre nell'ordine originale. Le "Idee per domande di ragionamento" sono facoltative.
> _Criteri:_
>
> - Dato che l'ordine casuale è attivo, Quando due studenti iniziano, Allora vedono ordini diversi.
> - Dato che cambio dispositivo, Quando riprendo, Allora l'ordine è lo stesso.
> - Dato che sono il docente, Quando correggo, Allora vedo l'ordine originale.
>
> _Perché:_ un sito non può bloccare le altre schede, ma mescolare rende inutile il "la terza è la B".
> _Scartato:_ blocco delle schede (impossibile); webcam (dati biometrici di minorenni).

> **FR-MAT-01 · File ammessi** (DOC-01, STU-01)
> PDF, Office senza macro, immagini e link video, fino a 25 MB. Visibili solo dopo il controllo di sicurezza.
> _Perché:_ un file infetto non deve arrivare agli studenti.

> **FR-SES-01 · PC condivisi** (STU-01, STU-02, STU-03)
> Studenti disconnessi dopo 20 minuti di inattività, con avviso, ma mai durante una verifica.
> _Perché:_ in laboratorio il PC lo usa poi un compagno.

> **FR-INC-01 · Misure del PDP** (DIR-02, DOC-02, STU-02)
> La direzione sceglie da un elenco le misure di uno studente: tempo aggiuntivo (10–50%), lettura ad alta voce, modalità concentrazione. **Mai la diagnosi.** Il tempo in più si applica da solo. Le misure le vedono solo la direzione e i docenti dello studente.
> _Criteri:_
>
> - Dato che ho +30%, Quando apro una verifica di 50 minuti, Allora ho 65 minuti.
> - Dato che sono un docente di un'altra classe, Quando cerco le misure, Allora è negato.
> - Dato che sono uno studente, Quando guardo un compagno, Allora non vedo le sue misure.
>
> _Perché:_ è un diritto (L. 170/2010) e la diagnosi è un dato sanitario (GDPR art. 9) che non serve.
> _Scartato:_ proroghe a mano del docente; salvare la diagnosi.

> **FR-INC-02 · Colore mai unico segnale** (tutte)
> Ogni informazione a colori ha anche icona e parola. Niente rosso contro verde. Grafici leggibili anche senza colori.
> _Perché:_ circa un ragazzo su dodici è daltonico.
> _Scartato:_ una "modalità daltonici" separata, da cercare e attivare.

### 5.4 Funzionalità per l'esperienza d'uso

Priorità: **Must** = indispensabile, **Should** = se resto nei tempi, **Could** = se avanza tempo.

| ID | Funzionalità | Per chi | Priorità | Storie |
| --- | --- | --- | --- | --- |
| FR-UX-01 | Pagina "Oggi" | Tutti | Should | DIR-04, DOC-03, STU-02 |
| FR-UX-02 | Griglia delle cattedre | Direzione | Should | DIR-03 |
| FR-UX-03 | Creazione guidata a passi, con bozza automatica | Direzione, docenti | Must | DIR-03, DOC-02 |
| FR-UX-04 | Importazione studenti da foglio di calcolo | Direzione | Should | DIR-02 |
| FR-UX-05 | Pulsante "Aa" e temi | Tutti | Must | tutte |
| FR-UX-06 | "Segui la verifica" in diretta | Docenti | Should | STU-02, DOC-03 |
| FR-UX-07 | Correzione domanda per domanda e commento al voto | Docenti | Should | DOC-03, STU-03 |
| FR-UX-08 | Duplicare una verifica su un'altra classe | Docenti | Could | DOC-02 |
| FR-UX-09 | Stesso materiale in più classi | Docenti | Could | DOC-01 |
| FR-UX-10 | Media, andamento e "Quanto mi serve?" | Studenti | Could | STU-03 |
| FR-UX-11 | Ricerca rapida (Ctrl+K) | Tutti | Could | tutte |
| FR-UX-12 | Avvisi nell'app | Tutti | Should | DIR-01, DOC-01, STU-01, STU-03 |
| FR-UX-13 | Aggiunta alla schermata Home | Studenti | Should | STU-02 |
| FR-UX-14 | Ordine casuale di domande e opzioni | Docenti, studenti | Must | DOC-02, STU-02 |
| FR-UX-15 | Idee per domande di ragionamento | Docenti | Could | DOC-02 |

### 5.5 Accessibilità e inclusione

| ID | Funzionalità | Per chi | Priorità | Storie |
| --- | --- | --- | --- | --- |
| FR-INC-01 | Misure del PDP automatiche | Studenti con DSA | Should | DIR-02, DOC-02, STU-02 |
| FR-INC-02 | Colore mai unico segnale | Daltonici, tutti | Must | tutte |
| FR-INC-03 | Pulsante 🔊 per ascoltare testi e domande | DSA, ipovedenti | Should | STU-01, STU-02 |
| FR-INC-04 | Spaziatura e righe corte regolabili | DSA, tutti | Should | STU-01, STU-02, STU-03 |
| FR-INC-05 | Modalità concentrazione in verifica | DSA, attenzione | Should | STU-02 |
| FR-INC-06 | Contatore del tempo nascondibile | Ansia da verifica | Could | STU-02 |
| FR-INC-07 | Tema ad alto contrasto | Ipovedenti | Could | tutte |
| FR-INC-08 | Carattere alternativo | DSA | Could | STU-01, STU-02 |
| FR-INC-09 | Animazioni ridotte se richiesto dal dispositivo | Tutti | Must | tutte |
| FR-INC-10 | Avviso per PDF scansionati | DSA, ipovedenti | Could | DOC-01, STU-01 |
| FR-INC-11 | Descrizione obbligatoria delle immagini | Ipovedenti | Should | DOC-02, STU-02 |
| FR-INC-12 | Tutto usabile da tastiera | Tutti | Must | tutte |

- **Dettatura:** non la costruisco io. Si usa quella della tastiera del dispositivo, così la voce dei ragazzi non va a servizi esterni.
- **Carattere "per dislessici":** è solo un'opzione. Aiuta di più la spaziatura.

---

## 6. Requisiti non funzionali

Numeri dalla stima del carico (sezione 8): circa 65 utenti normali, 150 al picco delle 9:00, obiettivo 300.

| ID | Famiglia | Requisito | Soglia e condizione | Come si verifica | Storie |
| --- | --- | --- | --- | --- | --- |
| NFR-01 | Prestazioni | Apertura verifica al picco | < 2 s per il 95%, con 150 utenti nello stesso minuto | Test di carico | STU-02 |
| NFR-02 | Prestazioni | Salvataggio risposta | < 1 s per il 95%, al picco | Test di carico | STU-02 |
| NFR-03 | Prestazioni | Pagine di consultazione | < 1,5 s per il 95% con 65 utenti; Panoramica < 3 s | Test di carico | STU-01, STU-03, DIR-04 |
| NFR-04 | Prestazioni | Telefono lento | "Oggi" usabile in < 4 s su Android economico in 3G | Prova con rete rallentata | STU-01, STU-02 |
| NFR-05 | Scalabilità | Oltre il picco | 300 utenti con le soglie di NFR-01/02 e < 1% di errori | Test di carico | STU-02, DOC-03 |
| NFR-06 | Disponibilità | Online in orario scolastico | 99,5% dalle 7:30 alle 14:30, lun–ven; niente aggiornamenti in quella fascia | Controllo ogni minuto | tutte |
| NFR-07 | Disponibilità | Nessun dato perso | 0 voti persi; ripristino degli ultimi 35 giorni, perdita massima 5 minuti | Prova di ripristino mensile | DOC-03, STU-02, STU-03 |
| NFR-08 | Sicurezza | Traffico cifrato | 100% su HTTPS | Scansione automatica | tutte |
| NFR-09 | Sicurezza | Permessi sul server | Ogni AC "negato" è rifiutato anche con chiamata diretta | Test automatici | tutte |
| NFR-10 | Sicurezza | Accessi protetti | Password ≥ 12 caratteri, non rubate; max 5 tentativi al minuto; secondo fattore per il personale | Test automatici | DIR-01, DIR-02 |
| NFR-11 | Sicurezza | PC condivisi | Disconnessione dopo 20 minuti, tranne in verifica | Test e prova in laboratorio | STU-01, STU-02, STU-03 |
| NFR-12 | Sicurezza | Nessun segreto nel codice | Development e Production separati, zero segreti nel sorgente | Controllo automatico | tutte |
| NFR-13 | Usabilità | Studenti autonomi | ≥ 90% completa una verifica e trova un voto senza aiuto | Osservazione al collaudo | STU-02, STU-03 |
| NFR-14 | Usabilità | Direzione autonoma | Classe completa creata in < 5 minuti, senza aiuto | Prova osservata | DIR-03 |
| NFR-15 | Usabilità | Gradimento | SUS ≥ 75, per studenti e personale | Questionario SUS | tutte |
| NFR-16 | Usabilità | Accessibile | Testo ≥ 16 px e zoom al 200%; pulsanti ≥ 44 px; contrasto ≥ 4,5:1; WCAG 2.2 AA | Test automatici e manuali | tutte |
| NFR-17 | Usabilità | Errori chiari | Ogni errore dice il campo e cosa scrivere | Revisione e collaudo | DIR-02, DOC-03 |
| NFR-18 | Ambientale | Dispositivi reali | Da 360 px; ultime 2 versioni di Chrome, Safari, Firefox, Edge; rete lenta | Prove su dispositivi | STU-01, STU-02 |
| NFR-19 | Ambientale | Pagine leggere | < 300 KB alla prima apertura | Controllo automatico | STU-01, STU-03 |
| NFR-20 | Supporto | Errori rintracciabili | Codice errore che ritrovo nei log in < 5 minuti | Prova al collaudo | tutte |
| NFR-21 | Supporto | API documentate | OpenAPI e collezione di test | Revisione | tutte |
| NFR-22 | Interazione | Elenchi paginati | 20 elementi di base, max 100 | Test sui servizi | DIR-04, STU-01, STU-03 |
| NFR-23 | Interazione | Errori uniformi | Stesso formato, codici coerenti | Test sui servizi | tutte |
| NFR-24 | Interazione | Stato sempre chiaro | In verifica: tempo e ultimo salvataggio visibili; conferma prima delle azioni irreversibili | Revisione schermate | STU-02, DOC-02, DIR-03 |
| NFR-25 | Conformità | GDPR | Solo nome, cognome, email, classe e misure PDP (mai diagnosi); dati in UE; violazioni segnalate per la notifica entro 72 ore | Revisione con il responsabile dati | tutte |
| NFR-26 | Conformità | Storico dei voti | Ogni correzione registra chi, quando, prima, dopo e motivo; non modificabile | Test automatici | DOC-03, DIR-04 |
| NFR-27 | Usabilità | Daltonismo | Nessuna informazione solo a colori; pagine comprensibili con simulatore e in grigi | Simulatore e prova al collaudo | tutte |
| NFR-28 | Usabilità | Spaziatura | Con la spaziatura WCAG 1.4.12 nessun testo si sovrappone o si taglia | Test automatico | STU-01, STU-02, STU-03 |
| NFR-29 | Interazione | Verifica senza mouse | Verifica completabile con tastiera e lettore di schermo; tempo annunciato ogni 5 minuti | Prova manuale | STU-02 |
| NFR-30 | Conformità | Misure PDP riservate | Visibili solo a direzione e docenti dello studente; letture e modifiche nello storico | Test sui permessi | DIR-02, STU-02 |

### 6.1 Requisiti impliciti

Si completa con le interviste al primo anno, a un docente e alla direzione, prima della versione 1.0. Domanda: _"Cosa daresti per scontato che un'app di questo tipo faccia sempre, o non faccia mai?"_

| Chi ho intervistato | Cosa ha detto | Requisito ricavato | Ipotesi da verificare |
| --- | --- | --- | --- |
| _[iniziali, studente]_ | _[…]_ | _[…]_ | Il voto non sparisce mai (NFR-07, NFR-26) |
| _[iniziali, studente]_ | _[…]_ | _[…]_ | Funziona dal telefono senza scaricare niente (NFR-18) |
| _[iniziali, studente]_ | _[…]_ | _[…]_ | I compagni non vedono i miei voti (NFR-09) |
| _[iniziali, studente con DSA]_ | _[…]_ | _[…]_ | Nessuno nota che ho il tempo in più (FR-INC-01) |
| _[iniziali, docente]_ | _[…]_ | _[…]_ | Non perdo la verifica se chiudo il browser (FR-UX-03) |
| _[iniziali, direzione]_ | _[…]_ | _[…]_ | Non cancello niente per sbaglio (FR-ACC-01) |

---

## 7. Assunzioni, vincoli e dipendenze

### 7.1 Assunzioni

| ID | Assunzione | Se è falsa |
| --- | --- | --- |
| ASS-01 | 590 studenti | Rifaccio carico e dimensionamento |
| ASS-02 | 58 docenti, 14 materie | Impatto minimo |
| ASS-03 | Direzione: direttore e vicario | Nessun impatto |
| ASS-04 | 26 classi da circa 23 studenti | Cambia il picco delle verifiche |
| ASS-05 | Lezioni 8:00–14:00, lun–ven | Cambiano disponibilità e orari di rilascio |
| ASS-06 | Al massimo 4 classi in verifica insieme | L'obiettivo di 300 utenti copre fino a circa 8 |
| ASS-07 | Wi-Fi instabile, molti usano la rete mobile | Se è peggio, verifiche in laboratorio via cavo |
| ASS-08 | Ogni studente ha telefono o PC in verifica | La scuola fornisce i PC del laboratorio |
| ASS-09 | Quasi tutti hanno un'email valida | Più lettere stampate |
| ASS-10 | La segreteria ha l'elenco iscritti in un foglio di calcolo | Inserimento a mano, nulla si blocca |
| ASS-11 | Esiste già un registro elettronico ufficiale | La scuola si aspetterebbe funzioni fuori perimetro |
| ASS-12 | Circa 5% con DSA, circa 8% dei ragazzi daltonici | Le funzioni di inclusione restano utili comunque |
| ASS-13 | Le misure PDP arrivano alla direzione a inizio anno | Si inseriscono man mano; intanto proroghe a mano |

### 7.2 Vincoli

| ID | Vincolo | Da dove viene |
| --- | --- | --- |
| VIN-01 | Budget = crediti cloud per studenti | Traccia |
| VIN-02 | Sviluppo da sola, insieme allo stage | Organizzazione del corso |
| VIN-03 | Prima il PRD validato, poi il codice | Traccia |
| VIN-04 | Online e pubblico per il collaudo | Traccia |
| VIN-05 | HTTPS e controllo dei ruoli nel backend | Requisiti trasversali |
| VIN-06 | Dati di minorenni, soggetti al GDPR | Normativa UE |
| VIN-07 | Consegna come repository | Docente del corso |
| VIN-08 | Interfaccia in italiano | Utenti italiani |
| VIN-09 | Diritto alle misure del PDP | L. 170/2010 |
| VIN-10 | Dati sanitari solo se strettamente necessari | GDPR art. 9 |

### 7.3 Dipendenze

| ID | Dipendenza | Serve entro | Chi |
| --- | --- | --- | --- |
| DIP-01 | Crediti cloud attivi | Prima versione online | Maria Laura Iacobucci |
| DIP-02 | Servizio email con dominio verificato | Collaudo | Maria Laura Iacobucci |
| DIP-03 | Dominio di ScuolaChill | Collaudo | Maria Laura Iacobucci |
| DIP-04 | PRD validato | Prima del codice | Docente del corso |
| DIP-05 | Studenti, docente e direzione per interviste e collaudo | Interviste prima della 1.0, collaudo a fine sviluppo | Maria Laura Iacobucci e docente del corso |
| DIP-06 | Parere del responsabile protezione dati | Prima dei dati reali | La scuola |
| DIP-07 | Elenco misure PDP con il referente per l'inclusione | Prima della 1.0 | Maria Laura Iacobucci e referente |

---

# Seconda parte · Il come

## 8. Stima del carico

### 8.1 Utenti concorrenti

| Situazione | Utenti | Da dove viene |
| --- | --- | --- |
| Giornata normale | circa 65 | 10% dei 650 utenti attivi in 5 minuti |
| Picco delle 9:00 | circa 150 | 4 classi × 23 = 92 in verifica, + 40 studenti, + docenti |
| Fine quadrimestre | circa 200 | Docenti che inseriscono voti, studenti che li controllano |
| **Obiettivo** | **300** | Il doppio del picco |

### 8.2 Richieste al secondo

- **Accessi alle 9:00:** circa 100 al minuto, meno di 2 al secondo. Sono lenti di proposito (calcolo della password).
- **Salvataggi in verifica:** 92 studenti ogni 15 secondi, circa 6 al secondo.
- **Apertura verifica:** 92 in 30 secondi, circa 3 al secondo.
- **Obiettivo 300:** sotto le 30 al secondo.

Un server piccolo basta. Le vere sfide sono tre: **non perdere dati**, **reggere le 9:00** senza avvii a freddo, **sicurezza**.

### 8.3 Profilo di carico

| Operazione | Frequente? | Pesante? | Critica? | Note |
| --- | --- | --- | --- | --- |
| Login | Sì, a ondate | Media | Sì | Calcolo password tarato per 100 accessi al minuto |
| Apertura verifica | Nei picchi | Leggera | Sì | Una query, pochi KB |
| Salvataggio risposta | Molto | Leggera | Sì | Una riga, aggiornata se esiste |
| Consegna verifica | Nei picchi | Leggera | Moltissimo | Transazione; il database impedisce la doppia consegna |
| "Segui la verifica" | In verifica | Leggera | No | Aggiornamento ogni 10 secondi |
| Panoramica | Raramente | Pesante | No | Dati precalcolati ogni 5 minuti |
| Caricamento materiale | Raramente | Pesante | No | Il file va diretto allo storage |
| Pagina voti | A ondate | Leggera | No | Vista già raggruppata |
| Importazione studenti | Rara | Media | No | Tutto o niente, in una transazione |

### 8.4 Spazio per anno

- **Materiale:** 58 docenti × 40 file × 3 MB ≈ 7 GB.
- **Database:** circa 35.000 voti e 350.000 risposte, sotto 1 GB.

---

## 9. Scelte tecnologiche

Criteri, in ordine: sicurezza di base, quanto conosco la tecnologia (o quanto costa impararla), adatta ai livelli richiesti, documentazione, costo.

| Area | Scelta | Alternativa | Perché |
| --- | --- | --- | --- |
| Backend | NestJS su Node.js, in TypeScript | ASP.NET Core; scartati Spring Boot, Express da solo, JavaScript senza tipi | Conosco JavaScript e Node.js dal corso; TypeScript aggiunge i tipi e me lo consigliano in azienda. NestJS ha già moduli, dependency injection, guard, Swagger e validazione. ASP.NET Core è più sicuro di base ma richiede C#. Express non dà struttura. |
| Frontend | React in TypeScript, con Vite, React Router, TanStack Query, React Hook Form + Zod, MUI, vite-plugin-pwa | Angular; scartati Vue e Next.js | React lo studio nel corso. Protegge di base dagli script iniettati. Le librerie coprono navigazione, chiamate con nuovi tentativi, form validati, componenti accessibili e uso offline. Angular non lo padroneggio; Vue non lo conosco; Next.js aggiunge un server inutile. |
| Database | PostgreSQL con Prisma | Azure SQL; scartati MongoDB e MySQL | Dominio relazionale con vincoli veri (chiavi, univocità, CHECK sui voti). Prisma fa query parametrizzate e migrazioni. Azure SQL serverless si spegne e alle 8:00 è freddo. MongoDB sposta l'integrità nel codice. MySQL non ha le viste materializzate. |
| Provider cloud | Microsoft Azure | AWS | Crediti studenti, region in Italia, segreti senza password, antivirus dei file incluso. AWS: niente crediti e permessi più complessi. |
| Servizi cloud | Container Apps (backend e processi), Static Web Apps, PostgreSQL Flexible, Blob Storage, Key Vault, Application Insights | App Service; scartati VM e Kubernetes | Container Apps: stessa immagine Docker del PC, HTTPS automatico, scala da solo, un'istanza sempre attiva. App Service scala solo nel piano più caro. Una VM va mantenuta a mano. Kubernetes è troppo per 650 utenti. |
| Regione | Italy North (Milano) | West Europe | Dati in Italia, latenza minima. West Europe come riserva, sempre in UE. |
| Servizi esterni | Azure Communication Services Email; Pwned Passwords | Brevo; elenco locale di password | Email con dati in Europa e senza chiavi da custodire. Pwned Passwords riceve solo 5 caratteri dell'hash; se non risponde, valgono le regole locali e niente si blocca. |
| Autenticazione | Modulo di accesso nel backend | Zitadel | I flussi sono molto specifici (account solo dalla direzione, lettera stampabile, disconnessione tranne in verifica). Zitadel sarebbe un sistema in più da gestire, con dati di minori. Il modulo resta sostituibile per le passkey in futuro. |
| Generazione PDF | PDFKit nel backend | Servizio esterno | La lettera ha un codice di attivazione: resta in casa. |
| Sintesi vocale | Sintesi vocale del browser, con voci italiane del dispositivo | Azure AI Speech | Gratis, funziona offline, il testo resta sul dispositivo. Azure costa e manda le verifiche fuori. |
| Font | Atkinson Hyperlegible, Fredoka, OpenDyslexic come opzione, ospitati con l'app | Google Fonts | Atkinson è pensato per la leggibilità. Ospitati in casa: niente IP degli studenti a Google, disponibili offline. |
| Controllo PDF | pdf.js nei processi in background | OCR esterno | Basta sapere se il PDF ha testo; gratis e senza terzi. |
| Test di carico | k6 | JMeter | Scenari in JavaScript, eseguibili nella pipeline. |

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
