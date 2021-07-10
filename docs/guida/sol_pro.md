# Soluzione problemi

#### Riga attiva di colore nero

Quando si usa VisiData su Windows Subsystem for Linux, la riga attiva risulta invisibile perché tutta nera.

Per fare in modo che torni "visibile" bisogna modificare il file di configurazione di VisiData. Questo file di _default_ non esiste: si deve trovare nella home dell'utente (quindi in `~`) e si deve nominare come `.visidatarc`.

Questi i passi:

```bash
## vai nella cartella home dell'utente
cd ~
## nano è un editor di testo, si installa con "sudo apt-get install nano.
## Si può esare usare qualsiasi editor per modificare il file
nano .visidatarc
```

Si aprirà il file `.visidatarc` a cui bisognerà aggiungere le stringhe sottostanti e poi salvare il file.

```
options.color_key_col=''
options.color_selected_row='yellow'
options.color_note_type='yellow'
options.color_graph_hidden='blue'
options.color_column_sep='blue'
options.null_value=""
options.color_key_col="blue"
```

#### Caratteri non leggibili in Windows Subsystem for Linux

Se si usa VisiData in Windows Subsystem for Linux, alcuni caratteri possono risultare non leggibili. Questo dipende dal font usato.

Per cambiarlo:

1. click con il destro del mouse sulla barra;
2. e scegliere Proprietà.

![](./imgs/cambiareCarattere.png)

Infine si consiglia il font di sotto:

![](./imgs/caratteriNonLeggibili.png)