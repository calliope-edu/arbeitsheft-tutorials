# 33 4_Licht

```package
v3
```

## Aufgabe @showdialog
Schreibe ein Programm, das den gemessenen Lichtwert bei ausgeschalteter LED-Matrix in eine Variable speichert und lasse dir den gespeicherten Wert danach auf der LED-Matrix anzeigen.

## Variable erstellen
Erstelle eine ``||variables.Variable||`` und benenne sie „Licht“.

![](https://calliope.cc/tutorials/variable_licht.png)

## Lichtstärke speichern @showdialog
Wenn Knopf A geklickt, speichere die gemessene Lichtstärke in die Variable „Licht“.

## Eingabe definieren
Wähle als Eingabe den Block ``||input.wenn Knopf A geklickt||``.

```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
})
```
## Verarbeitung: Lichtstärke messen und speichern
Der ``||input.Lichtstärke||`` Block gibt den gemessenen Lichtstärke Wert aus.
Verwende den ``||variables.setze Licht auf||`` Block, um den Wert der Variable auf die gemessene Lichtstärke zu setzen.


```blocks
input.onButtonEvent(Button.A, input.buttonEventClick(), function () {
Licht = input.lightLevel()
})
```

## Lichtstärke anzeigen @showdialog
Wenn Knopf B geklickt, zeige den Wert der Variable „Licht“ an.

## Eingabe definieren
Platziere einen weiteren Block ``|| input.Wenn Knopf A ||`` geklickt und ändere diesen in ``|| input.Wenn Knopf B ||`` geklickt.

```
```
![Knopf B](https://calliope.cc/tutorials/kopf_a_b.png)

## Ausgabe definieren
Verwenden den ``|| basic.zeige Zahl||`` Block und lasse dir den Wert der Variable ``||variables.Licht|`` ausgeben.

```blocks
input.onButtonEvent(Button.B, input.buttonEventClick(), function () {
basic.showNumber(Licht)
})
```

## Geschafft! 👏
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```template
//
```



























































