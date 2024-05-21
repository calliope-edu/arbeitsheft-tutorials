# 20 2_Raketenstart


## Aufgabe @showdialog
Verwende eine Variable, um die Geschwindigkeit deiner Animation zu bestimmen und bequem anzupassen, anstatt immer wieder in jedem Pause-Block die Geschwindigkeit zu ändern.

## Variable erstellen
Erstelle eine ``||variables.Variable||`` und benenne sie „Tempo“.

```
```
![](https://calliope.cc/tutorials/variable_tempo.png)

## Variable einfügen
Verwende den Block ``||variables.setze Tempo auf||``, um die Variable Tempo auf den Wert `100` zu setzen. Achtung: Platziere den Block vor deinem Countdown!

```blocks
let Tempo = 100
basic.showNumber(3)
basic.pause(100)
basic.showNumber(2)
basic.pause(100)
basic.showNumber(1)
basic.pause(100)
basic.showNumber(0)
```

## Ersetzen
Ersetze die Werte in den Pause-Blöcken durch die Variable ``||variables.Tempo||``.

```blocks
let Tempo = 100
basic.showNumber(3)
basic.pause(Tempo)
basic.showNumber(2)
basic.pause(Tempo)
basic.showNumber(1)
basic.pause(Tempo)
basic.showNumber(0)
```

## Countdown verlangsamen
Verlangsame deinen Countdown, indem du den Wert der Variable ``||variables.Tempo||`` auf `500` setzt.

```blocks
let Tempo = 500
basic.showNumber(3)
basic.pause(Tempo)
basic.showNumber(2)
basic.pause(Tempo)
basic.showNumber(1)
basic.pause(Tempo)
basic.showNumber(0)
```

## Geschafft! 🎉
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```template
basic.showNumber(3)
basic.pause(100)
basic.showNumber(2)
basic.pause(100)
basic.showNumber(1)
basic.pause(100)
basic.showNumber(0)
basic.pause(100)
basic.showLeds(`
 . . # . .
 . # # # .
 . # # # .
 . . # . .
 . # . # .
 `)
basic.showLeds(`
 . # # # .
 . # # # .
 . . # . .
 . # . # .
 . . . . .
 `)
basic.showLeds(`
 . # # # .
 . . # . .
 . # . # .
 . . . . .
 . . . . .
 `)
basic.showLeds(`
 . . # . .
 . # . # .
 . . . . .
 . . . . .
 . . . . .
 `)
basic.showLeds(`
 . # . # .
 . . . . .
 . . . . .
 . . . . .
 . . . . .
 `)
basic.showLeds(`
 . . . . .
 . . . . .
 . . . . .
 . . . . .
 . . . . .
 `)
```














































