# 45 1_Pflanzenstation

```package
v3
```

## Pflanzenstation @showdialog
Programmiere eine Pfanzenstation, die dir hilft, die Pflanzen im Klassenzimmer bestmöglich zu versorgen. Pflanzen brauchen **Wasser**, **Sonnenlicht** und auch die richtige
**Temperatur** spielt eine wichtige Rolle. 

## Temperatur messen @showdialog
**Temperatur** - Wird Knopf B gedrückt, lasse dir die Temperatur anzeigen.

## Temperatur messen
Um die Temperatur anzuzeigen, verwende den Block ``||input.wenn Knopf A geklickt||``. Ändere den Knopf, indem du auf das Dropdown-Menü von ``||input.wenn Knopf A geklickt||`` klickst und ``Taste B`` auswählst.   

```blocks
input.onButtonEvent(Button.B, input.buttonEventClick(), function () {
})
```

## Temperatur messen
Zeige dir die Temperatur an, indem der Eingabe-Block  ``||input.Temperatur||`` in den Block ``||basic.zeige Zahl||`` eingefügt wird.


```blocks
input.onButtonEvent(Button.B, input.buttonEventClick(), function () {
  basic.showNumber(input.temperature())
})
```

## Helligkeit messen @showdialog
- **Helligkeit** - Wird Knopf A gedrückt, lasse dir anzeigen, ob genügend Licht zur Verfügung
steht. Ist es zu dunkel, lasse eine Sonne auf der LED-Matrix erscheinen. Ist es hell genug, lasse ein Häkchen erscheinen.

## Helligkeit messen
Füge einen weiteren ``||input.wenn Knopf A geklickt||`` Block hinzu, um die gemessenen Helligkeitswerte auszugeben. Wähle eine ``||logic.wenn/dann||``-Verzweigung aus, um im nächsten Schritt die gemessenen Lichtwerte mit dem Grenzwert zu vergleichen.


```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
    if (true) {
    	
    } else {
    	
    }
})
```

## Messwerte vergleichen
Füge als Bedingung ``||input.Lichtstärke||`` > 50 ein, indem du einen ``||logic.logischen Vergleich||`` auswählst und dort die ``||input.Lichtstärke||`` mit der Zahl ``50`` vergleichst.

```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
  if (input.lightLevel() > 50) {
  } else {
})
```

## Ausgabe definieren
Ist es zu dunkel, lasse eine Sonne auf der LED-Matrix erscheinen. Ist es hell genug, lasse ein Häkchen erscheinen. Verwenden den ``||basic.zeige Symbol||`` Block, um die Symbole auf der LED-Matrix anzuzeigen.
```blocks
input.onButtonEvent(Button.B, input.buttonEventClick(), function () {
  if (input.lightLevel() > 50) {
      basic.showIcon(IconNames.Yes)
  } else {
      basic.showLeds(`
          # . # . #
          . # # # .
          # # # # #
          . # # # .
          # . # . #
          `)
  }
})
```

## Bodenfeuchtigkeit messen @showdialog
Prüfe dauerhaft: Ist die Erde zu trocken, lasse die RGB-LED rot leuchten, ansonsten lasse die RGB-LED grün leuchten. Verwende den Feuchtigkeitssensor und schließe ihn an den rechten Grove-Port A1 an.

## Bodenfeuchtigkeit messen
Platziere eine ``||logic.wenn/dann||``-Verzweigung in der ``||basic.dauerhaft||``-Schleife.

```blocks
basic.forever(function () {
  if (true) {
  } else {
  }
})
```

## Bodenfeuchtigkeit messen

Verwende den ``||grove.Feuchtigkeit||``-Block, um die Bodenfeuchtigkeit zu ermitteln.
**Hinweis:** Im Tutorial ist die ``||grove.Grove-Erweiterung||`` bereits integriert. Im Editor musst du sie erst hinzufügen.

## Messwerte vergleichen
Füge einen ``||logic.logischen Vergleich||`` in die ``||logic.wenn/dann||``-Verzweigung, in der geprüft wird, ob der ``||grove.Feuchtigkeit (analog)||`` > 300 ist. 


```blocks
basic.forever(function () {
 if (grove.measureMoistureAnalog(AnalogPin.C16) < 300) {
} else {
}


})
```

## Ausgabe definieren
Ist die Erde feucht, wird die Farbe auf grün gesetzt. Ist sie trocken auf rot. Platziere den Block ``||basic.setze Farbe auf||`` ein und wähle die Farbe in den entsprechenden Stellen in der ``||logic.wenn/dann||``-Verzweigung aus.

```blocks
basic.forever(function () {
if (grove.measureMoistureAnalog(AnalogPin.C16) < 300) {
      basic.setLedColor(0x00ff00)
  } else {
      basic.setLedColor(0xff0000)
  }
})
```

## Geschafft! 🎉
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.


```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
    if (input.lightLevel() > 50) {
        basic.showIcon(IconNames.Yes)
    } else {
        basic.showLeds(`
            # . # . #
            . # # # .
            # # # # #
            . # # # .
            # . # . #
            `)
    }
})
input.onButtonEvent(Button.B, input.buttonEventClick(), function () {
    basic.showNumber(input.temperature())
})
basic.forever(function () {
if (grove.measureMoistureAnalog(AnalogPin.C16) < 300) {
      basic.setLedColor(0x00ff00)
  } else {
      basic.setLedColor(0xff0000)
  }
})
```

```template
basic.forever(function () {
})
```


```package
grove=github:calliope-edu/pxt-grove
```





