# Lavorare sulle righe

La cosa più importante da comprendere è come selezionarle e deselezionarle, perché molte delle operazioni vengono  eseguite proprio su quelle selezionate.

I tasti principali di selezione sono:

- `s`, per selezionare la riga corrente;
- `u`, per deselezionare la riga corrente;
- `t`, per invertire la selezione della riga corrente;
- `gs`, per selezionare tutte le righe;
- `gu`, per deselezionare tutte le righe;
- `gt`, per invertire i criteri di selezione per tutte le righe.

![](../imgs/03_selezione.png)

#### Selezione di righe tramite espressione regolare

- `| + termine da ricercare`, seleziona tutte le righe in cui c'è corrispondenza per la colonna corrente;
- `\ + termine da ricercare`, deseleziona tutte le righe in cui c'è corrispondenza per la colonna corrente;
- `g| + termine da ricercare`, seleziona tutte le righe in cui c'è corrispondenza per una qualsiasi colonna;
- `g\ + termine da ricercare`, deseleziona tutte le righe in cui c'è corrispondenza per una qualsiasi colonna;
- `,`, dato il valore della cella selezionata, seleziona tutte le righe in cui per la colonna corrente c'è corrispondenza;
- `g,`, seleziona tutte le righe uguali a quelle corrente.

Se ad esempio:

- ci si sposta nella colonna `provincia_residenza`
- poi si pigia `|`;
- si digita `TERAMO`;
- si preme `Invio`.

... si ottiene qualcosa come quella di sotto.

![](../imgs/04_selezione.png)

#### Selezione di righe tramite espressioni Python

È possibile fare una selezione di righe tramite un'espressione di Python ([qui](https://docs.python.org/3/tutorial/introduction.html) per approfondire sui concetti di base delle espressioni).

I comandi da tastiera sono:

- `z|`, per selezionare tutte le righe in cui l'espressione è valida;
- `z\`, per deselezionare tutte le righe in cui l'espressione è valida.

Ad esempio seguendo questi step:

- `gu`, per deselezionare tutto;
- `z|`, per attivare la selezione tramite espressione Python;
- scrivendo `provincia_residenza == "PESCARA" and sesso == "F"`;
- e pigiando su `Invio`.

... verranno selezionati tutti gli elementi in cui la provincia è "Pescara" ed il sesso è "F".

#### Selezione di righe tramite espressioni Python e regex

- si digita `z|`;
- si scrive l'espressione, come ad esempio `re.search("^1", FieldB) and re.search("^2", FieldA)`, ovvero tutte le righe in cui il campo `FieldB` inizia per `1` e il campo `FieldA` per `2`.

#### Selezionare un numero random di righe

- aprire una tabella;
- fare click sulla barra spaziatrice;
- scrivere `random-rows` (si può scrivere anche soltanto ad esempio `ran` e autocompletare con `TAB`) e premere `INVIO`;
- scrivere il numero di righe random che si vogliono selezionare.

#### Spostare righe

Si fa con queste combinazioni:

- `Shift+j`, per spostare la riga corrente verso il basso;
- `Shift+k`, per spostare la riga corrente verso l'alto.

#### Cancellare righe

- `d` per cancellare la riga corrente;
- `gd` per cancellare le righe selezionate.

#### Modificare il contenuto

Questi i comandi di base:

- `e`, per modificare la cella corrente;
- `Enter`, per chiudere la modifica;
- `Control+c`, per cancellare la modifica;
- `Control+a`, per andare a inizio linea;
- `Control+e`, per andare a fine linea;
- `Control+k`, per cancellare il contenuto a partire dalla posizione del cursore.