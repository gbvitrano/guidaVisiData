# Moduli Python

VisiData è un foglio elettronico basato su Python 3. Questo consente di utilizzare al suo interno la galassia dei moduli disponibili per Python.

Per farlo, bisogna precaricare questi moduli all'avvio di VisiData. Questo si realizza modificando il file di configurazione del programma - si chiama `.visidatarc` - contenuto nella cartella _home_ dell'utente. Se si vuole ad esempio sfruttare il modulo `datetime`, si apre in modifica il file `.visidatarc` e si aggiunge la riga

    from datetime import datetime

Poi si salva il file e si fa partire VisiData.

Se ad esempio si vuole fare un'analisi sulla data di immatricolazione per mese a partire dalla colonna `data_immatricolazione` e si volesse sfruttare il modulo `datetime`, si può procedere in questo modo:

- si va nella colonna `data_immatricolazione`;
- si preme `=`;
- si scrive nel prompt `datetime.strptime(data_immatricolazione, '%Y-%m-%d %H:%M:%S').month` e si pigia `Invio`.

Si ottiene qualcosa come quella di sotto:

![](./imgs/26_moduli.png)

E a questo punto si può rinominare la colonna premendo `^`, scrivendo "mese" e poi premendo `Invio`. E poi creare il foglio delle frequenze della colonna `mese`, pigiando `Shift+f` e scoprire che in Abruzzo si immatricola soprattutto a gennaio.

![](./imgs/27_moduli.png)

**NOTA BENE**: le funzioni del modulo `datetime` sono disponibili in modo nativo per le colonne già impostate (come tipo) a data. Quanto scritto sopra vale soprattutto come guida al come precaricare e utilizzare un modulo Python in VisiData.
