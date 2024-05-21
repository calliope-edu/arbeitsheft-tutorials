# 50 2_Personenzähler


## Aufgabe @showdialog
Ist die Klasse vollzählig?
Überprüfe mit dem Ultraschallsensor, ob alle Kinder wieder im Klassenraum sind. Programmiere einen Personenzähler, um die Personen zu zählen, die den Klassenraum betreten.

## Variablen definieren
Erstelle zu Beginn zwei Variablen. Eine Variable ``||variables.Personenzähler||`` für die Anzahl der gezählten Personen und eine Variable ``||variables.komplett||``. 

```
```
![image/variable](image/variable)

## Variablen definieren
Setze die Variable ``||variables.Personenzähler||`` beim Start auf 0 und die Variable ``||variables.komplett||`` auf die Anzahl der Klassenkamerad:innen, z.B. 20. 

```blocks
let Personenzähler = 0
Personenzähler = 0
let komplett = 20
```

## Schritt 3
Miss dauerhaft die Entfernung. Sobald eine Person am Ultraschallsensor vorbei läuft und die Entfernung unter den Wert 10 fällt, erhöhe den Personenzähler um 1. Füge eine ``||logic.wenn/dann||``-Verzweigung in die ``||basic.Dauerhaft-Schleife||`` ein. 

```blocks
basic.forever(function () {
    if (true) {
    }
})
```

## Wert vergleichen
Verwende einen ``||logic.logischen Vergleich||`` Block, in dem der Wert des ``||grove.Ultraschallsensors||`` mit dem GrenzWert, z.B. ``10`` cm verglichen wird. 
**Hinweis:** In diesem Tutorial ist der Ultraschallsensor bereits hinzugefügt und du findest ihn unter den ``||grove.Grove-Blöcken||``.

```blocks
basic.forever(function () {
    if (grove.measureInCentimeters(DigitalPin.C16) < 10) {
    }
})
```

## Variable hochsetzen
Erhöhe die Variable ``||variables.Personenzähler||`` um 1, wenn der Wert des Ultraschallsensor, beispielsweise unter 10 liegt.


```blocks
basic.forever(function () {
    if (grove.measureInCentimeters(DigitalPin.C16) < 10) {
            Personenzähler += 1
    }
})
```

## Werte auswerten
Ist der Personenzähler kleiner als die maximale Anzahl der Schüler:innen in der Klasse, dann leuchtet die LED rot, ansonsten grün. Füge dieses Mal eine weitere ``||logic.wenn/dann/ansonsten||``-Verzweigung in die ``||basic.Dauerhaft-Schleife||`` ein. Teste darin ob die Variable ``||variables.Personenzähler||`` kleiner als die Variable ``||variables.komplett||`` ist.

```blocks
let Personenzähler = 0
Personenzähler = 0
let komplett = 20
basic.forever(function () {
    if (grove.measureInCentimeters(DigitalPin.C16) < 10) {
        Personenzähler += 1
    }
    if (Personenzähler < komplett) {
    } else {
    }
})
```

## Ausgabe definieren
Ist der Personenzähler kleiner als die Variable komplett, dann ``||basic.setze die RGB-LED Farbe||`` auf **rot**. Andernfalls auf **grün**. 


```blocks
let Personenzähler = 0
Personenzähler = 0
let komplett = 20
basic.forever(function () {
    if (grove.measureInCentimeters(DigitalPin.C16) < 10) {
        Personenzähler += 1
    }
    if (Personenzähler < komplett) {
        basic.setLedColor(0xff0000)
    } else {
        basic.setLedColor(0x00ff00)
    }
})
```

## Erweiterung: Zurücksetzen
Baue noch die Option ein den Personenzähler über ``||input.A+B gedrückt||`` zurückzusetzen, damit der ``||variables.Personenzähler||`` neu gestartet und wieder von ``0`` gestartet werden kann.

```blocks
input.onButtonEvent(Button.AB, input.buttonEventClick(), function () {
    Personenzähler = 0
})
```

## Variable anzeigen
Zuletzt lasse dir, wenn ``||input.Taste A gedrückt||`` wird auf der LED-Matrix anzeigen, wieviele Personen bereits gezählt wurden. 
Tipp: Verwende die Variable ``||variables.Personenzähler||`` 


```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
    basic.showNumber(Personenzähler)
})
```

## Geschafft! ✨
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen und den Personenzähler zu testen.


```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
    basic.showNumber(Personenzähler)
})
input.onButtonEvent(Button.AB, input.buttonEventClick(), function () {
    Personenzähler = 0
})
let Personenzähler = 0
Personenzähler = 0
let komplett = 20
basic.forever(function () {
    if (grove.measureInCentimeters(DigitalPin.C16) < 10) {
        Personenzähler += 1
    }
    if (Personenzähler < komplett) {
        basic.setLedColor(0xff0000)
    } else {
        basic.setLedColor(0x00ff00)
    }
})


```


```template
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
})
```


```package
grove=github:calliope-edu/pxt-grove
```



