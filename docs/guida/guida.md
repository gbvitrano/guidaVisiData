# La guida

VisiData è un **foglio elettronico a riga di comando**. Potrebbe suonare come una contraddizione, perché si accosta qualcosa con interfaccia ricca (come un foglio elettronico) a qualcosa di visualmente molto minimale. In realtà questa è **una delle idee forti** di questa applicazione, che prende il meglio di questi due mondi: l'approccio a griglia e multi tabella del primo, e la rapidità, l'immediatezza, l'essere _easy_ e "subito pronto" di un terminale.


Di base quindi bisogna prima aprire il terminale. Poi per aprire un file basta scrivere un comando con questa struttura:

    vd nomeFile.csv

A seguire soltanto un piccolo estratto sul come usarlo. Per approfondire ho creato un elenco di [URL consigliati](#url-consigliati).

VisiData si usa al 99% con la tastiera, quindi è bene che il <kbd>Caps Lock</kbd> non sia attivo: gli *shortcut* da tastiera non funzionerebbero correttamente (grazie [Salvatore Fiandaca](https://twitter.com/totofiandaca) per la nota).

#### Un esempio di apertura di un file grande

"Grande" in informatica non vuol dire niente, è come "salato" con un piatto di pasta.

Un CSV grande per il mio PC (un notebook del 2015, con processore i7 e 8 GB di RAM) - se voglio lavorarci in modo "visuale" con un foglio elettronico - potrebbe essere già un CSV da 500000 righe, che mi si apre dopo 1 minuto e 15 secondi e dove un "trova e sostituisci" diventa operazione molto lunga (uso LibreOffice Calc).

Ci sono anche limiti che non sono personali. Se per esempio provassi a lavorare con uno dei dataset del "[Parco Circolante dei veicoli](http://dati.mit.gov.it/catalog/dataset/parco-circolante-dei-veicoli)" in Italia scoprirei dei limiti strumentali. <br>Un esempio con i dati dell'[Abruzzo](http://geodata.mit.gov.it/datasets/parco_circolante_Abruzzo.csv): con il comando da shell `wc -l parco_circolante_Abruzzo.csv` leggo che è composto da 1170439 righe.
Con una regione "piccola" come questa si va già oltre il limite di Calc, che è di 1048576 righe. Se voglio comunque visualizzare 1048576 righe di questo dataset, sul mio PC sono necessari circa **5 minuti**.

Con **VisiData** lancio `vd parco_circolante_Abruzzo.csv` e lo visualizzo **in 1 secondo**. C'è il "trucco", che è  invero una delle buone scelte del progettista: il file viene aperto in modo asincrono, caricandone subito una porzione navigabile. In basso a destra (vedi sotto) viene dato conto della percentuale di avanzamento che porterà alla piena apertura (meno di 15 secondi).

![](./imgs/01_vdApertura.png)

Questo essere "subito pronto" lo rende uno strumento di grande comodità, che l'ha portato a essere uno dei miei quotidiani.<br>
Ribadisco però ancora un volta che il "grande" e la valutazione del tempo dipendono dagli obiettivi che si hanno, dalle proprie conoscenze di base e dall'_hardware/software_ che si ha a disposizione.

Per chiudere la tabella aperta e Visidata si pigia `q` sulla tastiera.

**NOTA BENE**: questo file con i dati sul "Parco Circolante dei veicoli" in Abruzzo, verrà usato in questa guida come dataset di base. Ne ho pertanto creato una copia di backup [qui](./dati/parco_circolante_Abruzzo.zip).

#### Navigare tra i dati

Per muoversi tra le celle si usano le 4 frecce direzionali dalla tastiera o (come vim, da cui nell'uso da tastiera VisiData prende molta ispirazione) `h`,`j`,`k`,`l`.

Per muoversi in modo più esteso:

- `g + freccia in basso` oppure `gj`, per andare all'ultima riga;
- `g + freccia in alto` oppure `gk`, per andare alla prima riga;
- `g + freccia a sinistra` oppure `gh`, per andare alla colonna più a sinistra;
- `g + freccia a destra` oppure `gl`, per andare alla colonna più a destra;
- `PageDown` oppure `Control + Shift + f`, una pagina in giù;
- `PageUp` oppure `Control + Shift + b`, una pagina in alto.

**NOTA BENE**: `g` è il tasto per i comandi "globali".

Per muoversi tramite ricerca testuale, sfruttando le espressioni regolari:

- `/ + regex`, cerca in avanti nella colonna corrente;
- `? + regex`, cerca indietro nella colonna corrente;
- `g/ + regex`,	cerca in avanti in tutte le colonne;
- `g? + regex`,	cerca indietro in tutte le colonne;

Con `n` e `N` si va avanti e indietro rispetto agli elementi di _output_ del risultato della ricerca.

Infine per saltare a una determinata riga o colonna, rispettivamente `zr` e `zc` seguito dal numero di riga e colonna (la numerazione inizia da zero).

### I fogli

In VisiData ci sono tre tipi di fogli:

- i fogli sorgente, con i dati che si è scelto di aprire con VisiData;
- i fogli derivati, come quelli derivanti da filtraggio o la tabelle con le frequenze (vedi sotto);
- i metafogli, che descrivono e definiscono i dataset caricati (come quello che descrive ad esempio le colonne di una tabella, o il "foglio dei fogli").

Il "foglio dei fogli" si apre con `Shift + s` e fornisce l'elenco (e alcune informazioni correlate) di tutti i fogli aperti. Selezionandone uno e pigiando `Invio`, quest'ultimo si aprirà.

![](./imgs/02_foglioDeiFogli.png)

Per rinominarne uno dal "foglio dei fogli", basta selezionarlo, premere `e` e inserire il nuovo nome e poi dare `Invio`. O in alternativa, se si è davanti al foglio che si vuole rinominare, premere la `barra spaziatrice`, scrivere `rename-sheet`, digitare il nuovo nome e infine pigiare su `Invio`.

Il foglio correntemente aperto si chiude con `q`.