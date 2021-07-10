# Creare un grafico di dispersione (scatter plot)

VisiData può stampare a schermo anche dei grafici XY. Non è un suo punto di forza, ma può essere utile per avere una prima e grezza visualizzazione spaziale dell'insieme dei dati.

Il requisito per crearne uno, è avere due colonne numeriche, da usare come coppia di coordinate. Qualcosa come quella di sotto.

| fid | X | Y |
| --- | --- | --- |
| 1 | 12.29 | 43.76 |
| 2 | 12.16 | 43.64 |
| 3 | 12.15 | 43.65 |
| 4 | 12.16 | 43.63 |
| ... | ... | ... |

Per generare il grafico basterà seguire i seguenti passi:

- impostare come numeriche (numeri decimali digitando `%` sulla colonna, o `#` per numeri interi) le due colonne con le coordinate;
- impostare come colonna chiave la colonna con le ascisse, selezionandola e digitando `!`;
- selezionare la colonna con le ordinate e digitare `.`.

In output si avrà qualcosa come quella di sotto

![](./imgs/scatterPlot.png)






