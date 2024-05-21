# 21 4_RGB-LED


## Aufgabe  @showdialog
Programmiere einen Regenbogen. Verwende dazu folgende Farben:
rot, orange, gelb, grün, türkis, blau, lila.

## Variable erstellen
Erstelle eine ``||variables.Variable||`` und benenne sie „Tempo“.

```
```
![](https://calliope.cc/tutorials/variable_tempo.png)

## Tempo einstellen
Verwende den Block ``||variables.setze Tempo auf||`` aus der Kategorie ``||variables.Variablen||``, um die Variable Tempo auf den Wert `100` zu setzen. Platziere den Block ganz zu anfangs in der ``||basic.Start Funktion||``.

```blocks
let Tempo = 100
```

## RGB-LED
Verwende den ``||basic.setze Farbe auf||`` Block und ziehe diesen in die ``||basic.Start Funktion||``. Stelle den Block so ein, dass die RGB-LED rot leuchtet.

```blocks
let Tempo = 100
basic.setLedColor(0xff0000)
```

## Pausenwert ersetzen
Füge einen ``||basic.pausiere||`` Block hinzu und ersetze den Pausenwert durch den Block ``||variables.Tempo||``.
```blocks
let Tempo = 100
basic.setLedColor(0xff0000)
basic.pause(Tempo)
```

## Regenbogen
Füge für jede weitere Farbe einen ``||basic.setze Farbe auf||`` Block und einen ``||basic.pausiere||`` Block hinzu.

```blocks
let Tempo = 100
basic.setLedColor(0xff0000)
basic.pause(Tempo)
basic.setLedColor(0xff8000)
basic.pause(Tempo)
basic.setLedColor(0xffff00)
basic.pause(Tempo)
basic.setLedColor(0x00ff00)
basic.pause(Tempo)
basic.setLedColor(0x00ffff)
basic.pause(Tempo)
basic.setLedColor(0x007fff)
basic.pause(Tempo)
basic.setLedColor(0xb09eff)
```

## Geschafft! ✨
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.


```template
//
```



















