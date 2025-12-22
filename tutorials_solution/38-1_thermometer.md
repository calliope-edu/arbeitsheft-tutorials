# 38 1b_Thermometer

```package
v3
```

## Aufgabe @showdialog
Schreibe ein Programm für ein Thermometer, das ein Hitzefrei-Signal ausgibt, wenn eine Temperatur von 30°C überschritten ist.🍦 


- Ist die gemessene **Temperatur > 30°C**, lasse ein Eis-Symbol auf der LED-Matrix erscheinen und schalte die RGB-LED auf `rot`.
- Ist die gemessene **Temperatur < 20°C**, schalte die LED-Matrix aus und die RGB-LED auf `blau`.
- In **allen anderen Fällen**, schalte die Hälfte der LED-Matrix ein und die RGB-LED auf `grün`.


## Abfrage erstellen
Wähle aus den Logik-Blöcken eine ``||logic.wenn dann ansonsten|``-Abfrage aus und füge sie in die ``||basic.dauerhaft||``-Schleife ein.
Klicke auf das **+** der Abfrage, um eine weitere Bedingung hinzuzufügen.


```blocks
basic.forever(function () {
  if (true) {

  } else if (true) {

  } else {

  }
})
```

## Bedingungen erstellen (warm)
Ersätze den ersten "wahr" Block in der Abfrage durch einen ``||logic.Vergleich (=)||`` Block, um die gemessenen ``||input.Temperatur|``  mit dem höchsten Schwellenwert zu vergleichen.
Ändere den Operator auf **>**.


```blocks
basic.forever(function () {
  if (input.temperature() > 30) {

  } else if (true) {

  } else {

  }
})
```

## Bedingungen erstellen (kalt)
Ersätze den zweiten "wahr" Block in der Abfrage durch einen ``||logic.Vergleich (=)||`` Block, um die gemessenen ``||input.Temperatur|``  mit dem niedrigsten Schwellenwert zu vergleichen.
Ändere den Operator auf **<**.

```blocks
basic.forever(function () {
  if (input.temperature() > 30) {

  } else if (input.temperature() < 20) {

  } else {

  }
})
```

## Ausgabe definieren
Vervollständige dein Programm, indem du für die unterschiedlichen Fälle die Ausgabe über die LED-Matrix und die RGB-LED hinzufügst.
Verwende die BLöcke ``||basic.zeige LEDs||`` und ``||basic.setze Farbe auf||``.


```blocks
basic.forever(function () {
  if (input.temperature() > 30) {
      basic.showLeds(`
          # # # # #
          # # # # #
          # # # # #
          # # # # #
          # # # # #
          `)
      basic.setLedColor(0xff0000)
  } else if (input.temperature() < 20) {
      basic.showLeds(`
          . . . . .
          . . . . .
          . . . . .
          . . . . .
          . . . . .
          `)
      basic.setLedColor(0x007fff)
  } else {
      basic.showLeds(`
          # . # . #
          . # . # .
          # . # . #
          . # . # .
          # . # . #
          `)
      basic.setLedColor(0x00ff00)
  }
})
```

## Geschafft! ✋
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.


```template
basic.forever(function () {
})
```



































