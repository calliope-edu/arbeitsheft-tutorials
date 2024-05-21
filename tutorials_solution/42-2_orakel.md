# 42 2 (Variante)_Orakel


## Aufgabe @showdialog
Gewinnen wir das nächste Hockeyturnier, ist Flynn verliebt in mich oder darf ich heute Abend am Computer spielen? Manche Antworten musst du sofort wissen.<br>
Baue dir dein eigenes **Calliope mini Orakel** und lasse dir die Antworten geben.
Du programmierst und bestimmst die Antworten!

## Eingabe definieren
Wähle als Eingabe den Block ``||input.wenn geschüttelt||``.

```blocks
input.onGesture(Gesture.Shake, function () {
})
```

## Variable Zufall erstellen
Erstelle eine ``||variables.Variable||`` und benenne sie Zufall.


```
```
![](https://calliope.cc/tutorials/variable_zufall.png)

## Zufällige Zahl generieren und speichern
Verwende den  ``||math.wähle eine zufällige Zahl||``-Block, um ein zufällige Zahl zwischen 1 und 3 zu ermitteln.
Speichere diese mit Hilfe des ``||variables.setze Zufall auf||`` Blocks in die Variable `Zufall`.

```blocks
let Zufall = 0
input.onGesture(Gesture.Shake, function () {
Zufall = randint(1,3)
})
```

## Bedingungen abfragen


Frage mit Hilfe einer ``||logic.wenn/dann||``-Verzweigung die zufällige Zahl ab. Verwende den ``||logic.Vergleich (=)||`` Block, um den Wert der Variablen ``||variables.Zufall||`` mit den möglichen Zahlen zu vergleichen. Du benötigst eine Abfrage für jede mögliche Zahl.<p>
**Tipp:** Du kannst auch eine Mehrfachverzweigung verwenden, wenn du auf das **+** klickst in der Abfrage klickst und diese erweiterst.

```blocks
let Zufall = 0
input.onGesture(Gesture.Shake, function () {
Zufall = randint(0, 2)
if (Zufall == 1) {


}
if (Zufall == 2) {


}
if (Zufall == 3) {


}
```

## Ausgabe definieren
Jeder möglichen Zahl wird eine Antwort zugewiesen. Die zufällige Zahl bestimmt die Antwort. Verwende den  ``||basic.zeige Text||``-Block, um die Antwort auf der LED-Matrix anzuzeigen.

```blocks
let Zufall = 0
input.onGesture(Gesture.Shake, function () {
Zufall = randint(0, 2)
if (Zufall == 1) {
   basic.showString("Ja")
}
if (Zufall == 2) {
   basic.showString("Nein")
}
if (Zufall == 3) {
   basic.showString("Vielleicht")
}

```
## Geschafft! 🎉
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```template
//
```



















