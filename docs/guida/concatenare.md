# Concatenare tabelle

La concatenazione tra due o più tabelle con la stessa struttura si attiva tramite `&`. Ad esempio, a partire dai due file `inputFileOne.csv` e `inputFileTwo.csv`, presenti [qui](https://github.com/ondata/guidaVisiData/tree/master/dati) si procede in questo modo:

- si apre la shell e si va nella cartella che contiene i file da concatenare;
- si scrive `vd` e si preme `Invio`;
- si seleziona la prima voce `DirSheet for the current directory` e si preme `invio`;
- si selezionano con `s` i due file;
- si preme `g Invio` per aprirli entrambi;
- si apre il foglio dei fogli con `Shift+s`;
- si selezionano  `inputFileOne.csv` e `inputFileTwo.csv` con `s`;
- si preme `&` per attivare la concatenazione;
- si preme `Ctrl+X` per il menu;
- si seleziona `append` e poi si preme `Invio`.

Si avrà a video l'unione dei due file di input (in [questo video](http://youtu.be/NJ8FBYI-WGE?hd=1) una replica di quanto descritto, per versioni `vd < 2`).
