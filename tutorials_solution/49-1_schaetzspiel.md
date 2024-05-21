# 49 1_Schätzspiel


## Schätzspiel @showdialog
Programmiere ein Schätzspiel, das die Entfernung zwischen zwei Objekten misst. Der
Calliope mini misst die Entfernung - im Geheimen. Du schätzt die Entfernung und der Calliope mini löst auf und zeigt die gemessene Entfernung an. 


## Aufgabe @showdialog
Mit Taste A wird die Entfernung gemessen und in eine Variable gespeichert. Über die Taste B wird der gespeicherte Wert der Variable auf dem Display angezeigt.


## Tasten Ereignisse hinzufügen
Füge den Block ``||input.wenn Knopf A geklickt||`` zwei Mal ein und ändere bei einem Block die Taste zu ``B``. Tipp: Du kannst den Block mit Rechtklick duplizieren.


```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
})
input.onButtonEvent(Button.B, input.buttonEventClick(), function () {
})
```

## Variable definieren
Um die Entfernung beim Tastendruck zu speichern und später wieder abzurufen, erstelle eine ``||variable.Variable||`` und nenne diese *Entfernung*. 

```
```
![image/variable](image/variable)

## Entfernung speichern
Verwende den ``||grove.Ultraschallsensors||``-Block, um die Entfernung zu ermitteln.
**Hinweis:** Im Tutorial ist die ``||grove.Grove-Erweiterung||`` bereits integriert. Im Editor musst du sie erst hinzufügen.

Wenn Knopf ``||input.A geklickt||`` wird, speichere den gemessenen Wert mit Hilfe des ``||variable.setze Entfernung auf||`` Blocks in die Variable `Entfernung`.


```blocks
let Entfernung = 0
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
   Entfernung = grove.measureInCentimeters(DigitalPin.C16)
})
```

## Wert speichern
Rufe nun den gespeicherten Wert aus der Variable ``||variables.Entfernung||`` ab und zeige ihn auf dem Display an, wenn Taste B gedrückt wird. Verwende dazu den Block ``||basic.zeige Zahl||`` und füge ihn samt der Variable in den Block ``||input.wenn Knopf B geklickt||`` ein.


```blocks
let Entfernung = 0
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
   Entfernung = grove.measureInCentimeters(DigitalPin.C16)
})
```

## Testen
Teste dein Programm! Dir wird auffallen, dass die Werte des Ultraschallsensor ziemlich lang sind. Die Werte sind sehr genau und werden noch nicht gerundet. 
``||Math.Runde||`` den Wert des Ultraschallsensors, den du in der Variable speicherst ``||variables.setze Entfernung auf||``. Diesen findest du unter ``||math.Mathematik||``.


```blocks
let Entfernung = 0
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
   Entfernung = Math.round(grove.measureInCentimeters(DigitalPin.C16))
})
```

## Fragezeichen anzeigen
Lasse zuletzt dauerhaft ein „?“ auf der LED-Matrix erscheinen. Zeichne ein ? mit dem Block ``||basic.zeige LEDs||``.




```blocks
basic.forever(function () {
    basic.showLeds(`
        . # # . .
        . . . # .
        . . # . .
        . . . . .
        . . # . .
        `)
})
```


## Geschafft! 👏
Klicke auf ``|Herunterladen|``, teste dein Programm auf dem Calliope mini und versuche die Entfernung richtig zu schätzen!


```blocks
let Entfernung = 0
input.onButtonEvent(Button.A, input.buttonEventValue(ButtonEvent.Click), function () {
    Entfernung = Math.round(grove.measureInCentimeters(DigitalPin.C16))
})
input.onButtonEvent(Button.B, input.buttonEventValue(ButtonEvent.Click), function () {
    basic.showNumber(Entfernung)
})
basic.forever(function () {
    basic.showLeds(`
        . # # . .
        . . . # .
        . . # . .
        . . . . .
        . . # . .
        `)
})
```


```template
basic.forever(function () {
})
```


```package
grove=github:calliope-edu/pxt-grove
```













