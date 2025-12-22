# 42 2 (Variante)_Orakel

```package
v3
```

## Aufgabe @showdialog
Gewinnen wir das nächste Hockeyturnier, ist Flynn verliebt in mich oder darf ich heute Abend am Computer spielen? Manche Antworten musst du sofort wissen.<br>
Baue dir dein eigenes **Calliope mini Orakel** und lasse dir die Antworten geben.
Du programmierst und bestimmst die Antworten!

## Eingabe definieren
Wähle als Eingabe den Block ``||input.wenn geschüttelt||``.

## Variable Zufall erstellen
Erstelle eine ``||variables.Variable||`` und benenne sie Zufall.


```
```
![](https://calliope.cc/tutorials/variable_zufall.png)

## Zufällige Zahl generieren und speichern
Verwende den  ``||math.wähle eine zufällige Zahl||``-Block, um ein zufällige Zahl zwischen 1 und 3 zu ermitteln.
Speichere diese mit Hilfe des ``||variables.setze Zufall auf||`` Blocks in die Variable `Zufall`.


## Bedingungen abfragen

Frage mit Hilfe einer ``||logic.wenn/dann||``-Verzweigung die zufällige Zahl ab. Verwende den ``||logic.Vergleich (=)||`` Block, um den Wert der Variablen ``||variables.Zufall||`` mit den möglichen Zahlen zu vergleichen. Du benötigst eine Abfrage für jede mögliche Zahl.<p>
**Tipp:** Du kannst auch eine Mehrfachverzweigung verwenden, wenn du auf das **+** klickst in der Abfrage klickst und diese erweiterst.


## Ausgabe definieren
Jeder möglichen Zahl wird eine Antwort zugewiesen. Die zufällige Zahl bestimmt die Antwort. Verwende den  ``||basic.zeige Text||``-Block, um die Antwort auf der LED-Matrix anzuzeigen.

## Geschafft! 🎉
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```template
//
```



















