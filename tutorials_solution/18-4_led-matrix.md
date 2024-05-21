# 18.4-5 Raketenstart

## Aufgabe @showdialog
Lasse eine Rakete auf der LED-Matrix steigen. Du musst wie ein Trickfilmprofi in Einzelbildern denken.


## Symbol erstellen
Verwende den ``||basic.zeige LEDs||`` Block, um eine Rakete anzuzeigen.


```blocks
basic.showLeds(`
. . # . .
. # # # .
. # # # .
. . # . .
. # . # .
`)
```

## Animation erstellen
Erstelle Einzelbilder der Animation. Dupliziere dazu den ``||basic.zeige LEDs||`` Block und verschiebe die Pixelreihen von unten nach oben, jeweils um eine Zeile.


```blocks
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

## Countdown
Lasse vor der Raketenanimation einen Countdown von 3-2-1-0 anzeigen. Verwende den ``||basic.zeige Zahl||`` Block.


```blocks
basic.showNumber(3, 500)
basic.showNumber(2, 500)
basic.showNumber(1, 500)
basic.showNumber(0, 500)
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


## Geschafft! 👍
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.


```template
//
```

