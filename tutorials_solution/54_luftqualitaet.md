 # 54_Luftqualität

## Aufgabe @showdialog
Die Luft, die dich umgibt, spielt eine große Rolle für dein Wohlbefinden.
Programmiere eine Anzeige, die dich informiert, wenn es zu heiß wird, die Luftfeuchtigkeit
zu hoch oder zu niedrig ist und wenn mal wieder gelüftet werden muss.

## Temperatur messen @showdialog
Fange mit der Temperaturmessung an und nutze den Lautsprecher für den Temperaturhinweis.
Lasse einen Warnton ausgeben, wenn die Temperatur zu kalt oder zu warm ist.

## Temperatur messen
Damit ein Ton abgespielt werden kann, wenn die Temperatur z.B. über 30 °C steigt, wird eine ``||logic.wenn/dann/ansonsten||``-Verzweigung aus den ``||logic.Logikblöcken.||`` benötigt. Um die Temperatur permanent messen und vergleichen zu können, füge die Verzweigung in die ``||basic.dauerhaft||``-Schleife ein. 

```blocks
basic.forever(function () {
    if (true) {
    	
    } else {
    	
    }
})
```

## Messwert vergleichen
Füge einen ``||logic.logischen Vergleich||`` ein, womit du die gemessene ``||SCD40.Temperatur des CO2 Sensors||`` mit einem Grenzwert vergleichst. Ist die Temperatur z.B. > 30, lasse ein ``||music.Warnton||`` abgespielt werden. Verwende dazu einen ``||music.spiele Note||``-Block.

```blocks
basic.forever(function () {
    if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) > 30) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
    	
    }
})

```

## Verzweigung hinzufügen
Klicke in der ``||logic.Verzweigung||`` auf das ``||logic.+.||``, um eine weitere Bedingung hinzuzufügen, damit auch ein Warnton angespielt wird, wenn es zu kalt ist und die ``||SCD40.Temperatur||`` z.B. unter 18 Grad fällt. 

```blocks
basic.forever(function () {
    if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) > 30) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) < 18) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
    	
    }
})
```

## Ausgabe definieren
Füge in dem ``||logic.ansonsten||``-Abschnitt eine ``||music.Pause||`` ein, damit kein Warnton abgespielt wird, wenn die Temperatur weder zu warm noch zu kalt ist. 

```blocks
basic.forever(function () {
    if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) > 30) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) < 18) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
        music.rest(music.beat(BeatFraction.Whole))
    }
})
```

## CO2-Gehalt messen @showdialog
Prima, du hast die Temperaturmessung geschafft! 👍 Die CO2-Ampel funktioniert ganz ähnlich. Anstatt der Temperatur wird jetzt der CO2- Gehalt gemessen und anstatt Töne abzuspielen, leuchtet die RGB-LED.

## CO2-Gehalt messen
Der CO2-Gehalt in der Luft wird in ppm (Parts per Million/Teile pro Millionen) ausgegeben. Alles unter 1000 ppm ist unbedenklich.

## Messwert vergleichen
Erstelle eine zweite ``||logic.logische Verzweigung||`` und vergleiche den gemessenen ``||SCD40. CO2-Gehalt||`` mit den Grenzwerten. Ist der Wert über 2000, lasse die ``||basic.RGB-LED||`` rot leuchten. Ist dieser unter 1000, lasse sie grün leuchten. Ist der Wert dazwischen, leuchtet sie gelb.

```blocks
basic.forever(function () {
    if (SCD40.get_co2() < 1000) {
        basic.setLedColor(0x00ff00)
    } else if (SCD40.get_co2() > 2000) {
        basic.setLedColor(0xff0000)
    } else {
        basic.setLedColor(0xffff00)
    }
})
```

## Luftfeuchtigkeit messen @showdialog
Im nächsten Schritt wird die Luftfeuchtigkeit gemessen. Verwende die LED-Matrix für die Anzeige der Luftfeuchtigkeit. Angenehm fühlt es sich zwischen 30% und 70% an
Fülle die Balken der LED-Matrix entsprechend zu der prozentualen Luftfeuchtigkeit auf.

## Verzweigungen hinzufügen @showdialog
Füge eine dritte ``||logic.wenn/dann||``-Verzweigung in den ``||basic.dauerhaft||``-Block ein.
Klicke auf das ``||logic.+||`` , um die fünf Bedingungen einzufügen und eine Mehrfachverzweigung zu erstellen. 

*In einer Mehrfachverzweigung werden die Bedingungen von oben nach unten geprüft. Sobald eine wahr ist, wird der Codeblock der entsprechenden Bedingung ausgeführt und die darunterliegenden ignoriert. Deshalb ist die Reihenfolge der Bedingungen wichtig.*

## Messwert vergleichen
Lese den ``||SCD40.Luftfeuchtigkeit||`` aus und vergleich ihn in den Bedingungen. 

< 30 %, LED-Matrix leer sein
< 40 %, ein Balken ausgefüllt
< 50 %, zwei Balken ausgefüllt usw.
> 70 %, schalte die ganze LED-Matrix an

```blocks
basic.forever(function () {
    if (SCD40.get_relative_humidity() < 30) {
    	
    } else if (SCD40.get_relative_humidity() < 40) {
    	
    } else if (SCD40.get_relative_humidity() < 50) {
    	
    } else if (SCD40.get_relative_humidity() < 60) {
    	
    } else if (SCD40.get_relative_humidity() < 70) {
    	
    } else {
    	
    }
})

```

## Ausgabe definieren
Verwende den Block ``||basic.zeige LEDs||`` um die Balken in der LED-Matrix aufzufüllen.

```blocks
basic.forever(function () {
    if (SCD40.get_relative_humidity() < 30) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . . . .
            . . . . .
            . . . . .
            `)
    } else if (SCD40.get_relative_humidity() < 40) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . . . .
            . . . . .
            # # # # #
            `)
    } else if (SCD40.get_relative_humidity() < 50) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . . . .
            # # # # #
            # # # # #
            `)
    } else if (SCD40.get_relative_humidity() < 60) {
        basic.showLeds(`
            . . . . .
            . . . . .
            # # # # #
            # # # # #
            # # # # #
            `)
    } else if (SCD40.get_relative_humidity() < 70) {
        basic.showLeds(`
            . . . . .
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
    } else {
        basic.showLeds(`
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
    }
    basic.pause(60000)
})
```

## Zeitintervall festlegen
Prima! Du hast es fast geschafft. Füge in der Dauerhaftschleife noch eine ``||basic.Pause||`` ein, damit die Sensorwerte in einem bestimmten Zeitintervall aktualisiert werden.
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```blocks
basic.forever(function () {
    if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) > 30) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else if (SCD40.get_temperature(SCD40.SCD40_T_UNIT.C) < 18) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
        music.rest(music.beat(BeatFraction.Whole))
    }
    if (SCD40.get_co2() < 1000) {
        basic.setLedColor(0x00ff00)
    } else if (SCD40.get_co2() > 2000) {
        basic.setLedColor(0xff0000)
    } else {
        basic.setLedColor(0xffff00)
    }
    if (SCD40.get_relative_humidity() < 30) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . . . .
            . . . . .
            . . . . .
            `)
    } else if (SCD40.get_relative_humidity() < 40) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . . . .
            . . . . .
            # # # # #
            `)
    } else if (SCD40.get_relative_humidity() < 50) {
        basic.showLeds(`
            . . . . .
            . . . . .
            . . . . .
            # # # # #
            # # # # #
            `)
    } else if (SCD40.get_relative_humidity() < 60) {
        basic.showLeds(`
            . . . . .
            . . . . .
            # # # # #
            # # # # #
            # # # # #
            `)
    } else if (SCD40.get_relative_humidity() < 70) {
        basic.showLeds(`
            . . . . .
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
    } else {
        basic.showLeds(`
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            # # # # #
            `)
    }
    basic.pause(60000)
})
```

## Funktionen erstellen  @showdialog
Damit das Programm übersichtlicher wird, erstelle drei ``||function.Funktionen||`` für die Messung: Temperatur, CO2-Gehalt und Luftfeuchtigkeit.

![functions](https://calliope.cc/tutorials/funktion_erstellen.png)

## Variablen erstellen
Speichere außerdem den Sensorwert einmal in einer ``||variables.Variable||``, um ihn nicht mehrfach auszulesen. Erstelle eine Variable für den jeweiligen Sensorwert: Temperatur, Luftfeuchtigkeit und CO2-Gehalt und implementiere sie in den Funktionen.

```blocks
let temperatur = 0
function Temperatur_messen () {
    temperatur = SCD40.get_temperature(SCD40.SCD40_T_UNIT.C)
    if (temperatur > 30) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else if (temperatur < 18) {
        music.playTone(262, music.beat(BeatFraction.Whole))
    } else {
        music.rest(music.beat(BeatFraction.Whole))
    }
}
```

## Funktionen aufrufen 
Zu guter Letzt müssen die ``||function.Funktionen||`` in der ``||basic.dauerhaft||``-Schleife aufgerufen werden, damit die Sensormessung erfolgt.


```blocks
basic.forever(function () {
    Temperatur_messen()
    basic.pause(60000)
})
```

## Geschafft! 👏
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.


```template
basic.forever(function () {
})
```

```package
co2sensor=github:calliope-edu/co2-sensor-scd40
```



