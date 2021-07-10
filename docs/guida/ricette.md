# Ricette

#### Salvare una tabella HTML in CSV, a partire da una pagina web

In questo esempio il presupposto è che si voglia trasformare in CSV una tabella HTML presente in una pagina web, in cui ci sono più tabelle. Il punto di partenza è quello di estrarre dalla pagina sorgente, una pagina HTML che contiene soltanto la tabella di interesse.

La pagina di esempio è:<br><https://web.archive.org/web/20190618071304/http://www.sias.regione.sicilia.it/NHEOWLH140_00_1.html>

Questa è composta da diverse tabelle.

![](./imgs/table.png)

Quella di interesse è l'unica composta da più di 7 colonne, e la query XPATH per estrarla è `//table[count(tr/td)>7]`.

La pagina di origine ha l'*encoding* in `ISO-8859-1`, ed è da convertire in `UTF-8`.

Per scaricare la pagina, cambiarne l'*encoding* ed estrarre la tabella di interesse il comando può essere

```bash
curl "http://www.sias.regione.sicilia.it/NHEOWLH140_00_1.html" | \
iconv -f ISO-8859-1 -t utf-8  | \
scrape -be '//table[count(tr/td)>7]'
```

L'*utility* usata sopra per fare la *query* `XPATH` è [scrape-cli](https://github.com/aborruso/scrape-cli).<br>
In output si ha una pagina web che contiene soltanto la tabella di interesse.

Per passarla a VisiData bisognerà modificare così lo script:

```bash
curl "http://www.sias.regione.sicilia.it/NHEOWLH140_00_1.html" | \
iconv -f ISO-8859-1 -t utf-8  | \
scrape -be '//table[count(tr/td)>7]' | \
vd -f html
```

Come risultato si aprirà la finestra di sotto. Per aprire la tabella sarà necessario premere `INVIO` e poi si potrà salvare la tabella in CSV (o altri formati) digitando `CTRL+ s`.

![](./imgs/htmltable.png)

Se si vuole inserire nello script anche la procedura di salvataggio, bisogna modificare lo script in questo modo:

```bash
curl "http://www.sias.regione.sicilia.it/NHEOWLH140_00_1.html" | \
iconv -f ISO-8859-1 -t utf-8  | \
scrape -be '//table[count(tr/td)>7]' | \
vd -b -f html -o out.csv -p dive.vd
```

Note:

- `-b` è per eseguire VisiData senza interfaccia;
- `-p dive.vd` per eseguire dei comandi (qui semplicemente l'apertura della tabella a partire dalla finestra iniziale di sopra).

Nel file [`dive.vd`](./dati/dive.vd) c'è il seguente contenuto.

```
sheet	col	row	longname	input	keystrokes	comment
			open-file	-	o
-		0	dive-row		^J
```

Il file di sopra è un file di log di VisiData (vedi [sezione dedicata](#Salvare-un-flusso-di-lavoro)). Tutte le operazioni fatte in VisiData finiscono in un log che può essere visualizzato e salvato. Quindi è possibile salvare la visualizzazione dell'elenco delle tabelle e poi l'apertura di quella di interesse.

Per creare questo di sopra:

- arrivare a visualizzare la tabella su VisiData;
- digitare `INVIO`;
- digitate `SHIFT + d` per visualizzare il log dei comandi;
- e infine `CTRL + s` per salvare il file `dive.vd`.