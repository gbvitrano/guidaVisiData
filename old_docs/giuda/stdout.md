# Fare il redirect dell'output verso lo stdout

Il comando

```
vd input.csv -b --save-filetype json | jq .
```

invierà ad esempio a `jq` un *output* `JSON` a partire dal CSV di *input*.

Se ad esempio si vuole passare l'output a grep:

```
vd input.csv -b --save-filetype tsv 2> /dev/null | grep 'a'
```

`2> /dev/null` per non avere `stderr` a schermo.