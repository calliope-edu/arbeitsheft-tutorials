# 35 1_Smart-Licht

```package
v3
```

## Aufgabe @showdialog
Schreibe ein Programm für eine Lampe, die durch das Klatschen in die Hände eingeschaltet und nach 5 Sekunden automatisch wieder ausgeschaltet wird.👏

## Abfrage erstellen
Wähle aus den Logik-Blöcken eine ``||logic.wenn dann ansonsten||`` Abfrage aus und füge sie in die ``||basic.dauerhaft||``-Schleife ein.
<br>
Über eine dauerhafte Abfrage der gemessenen Lautstärke Werte wird das Klatschen erkannt.

```blocks
basic.forever(function () {
  if (true) {

  } else {

  }
})

```


## Bedingung erstellen
Definiere einen Schwellenwert, z.B. `20` für die Lautstärke deines Klatschens!
Ersätze den “wahr” Block in der Abfrage durch einen ``||logic.Vergleich (=)||`` Block, um die gemessenen ``||input.Lichtstärke|``  mit dem Schwellenwert zu vergleichen.

```blocks
basic.forever(function () {
if (input.lightLevel() > 20) {

} else {

}
})
```

## Licht anschalten
Verwende den ``||basic.zeige LEDs||`` Block und fülle die gesamte Matrix aus, um das Licht anzuschalten.
Ergänze anschließend einen ``||basic.pausiere||``-Block und setze diesen auf `5000` ms, damit das Licht für 5 Sekunden an bleibt.

```blocks
basic.forever(function () {
if (input.lightLevel() > 20) {
      basic.showLeds(`
        # # # # #
        # # # # #
        # # # # #
        # # # # #
        # # # # #
        `)
    basic.pause(5000)
} else {

}
})
```

## Licht ausschalten
Schalte das Licht wieder aus, wenn die Bedingung nicht zutrifft. Verwende den ``||basic.Bildschirminhalt löschen||`` Block unter ``||basic.… mehr||``.<p>
Du kannst auch den ``||basic.zeige LEDs||`` Block verwenden und die Matrix leeren.


```blocks
basic.forever(function () {
if (input.lightLevel() > 20) {
    basic.showLeds(`
        # # # # #
        # # # # #
        # # # # #
        # # # # #
        # # # # #
        `)
    basic.pause(5000)
} else {
  basic.clearScreen()
}
})
```

## Geschafft! 👍
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```template
basic.forever(function () {
})
```



