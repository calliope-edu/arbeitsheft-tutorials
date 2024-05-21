# 27 1_Klavier


## Aufgabe @showdialog
Entwickle ein Calliope mini Klavier, das beim Berühren der Touch-Pins 0-3 jeweils eine unterschiedliche Note abspielt, die RGB-LED in verschiedenen Farben leuchten lässt und den Notennamen auf der LED-Matrix anzeigt.


## Startbild
Starte dein Programm mit einer Note, die als ``||basic.Symbol||`` auf der LED-Matrix angezeigt wird.

## Eingabe definieren
Wähle als Eingabe den Block ``||input.wenn Pin P0 gedrückt||``.

## Ausgabe definieren
Verwende für den Buchstaben der Note den ``||basic.zeige Text||`` Block und für die Farbe den  ``||basic.setze Farbe auf||`` Block.
Füge einen ``||music.spiele Note||``-Block für die Tonausgabe hinzu. Platziere die drei Ausgabe-Blöcke innherhalb des ``||input.wenn Pin P0||`` Eingabe-Blocks.

## Dupliziere @showdialog
Dupliziere die Programmblöcke und auch die weiteren Touch-Pins (1-3) zu steuern.

```
```
![](https://calliope.cc/tutorials/duplizieren.png)


## Ausgabe anpassen
Ändere die transparenten ``||input.wenn Pin P0 ||`` Blöcke nacheinander in: ``||input.wenn Pin P1||``, ``||input.wenn Pin P2||`` und ``||input.wenn Pin P3||``.
Passe die Notennamen, die Farben und die Tonausgabe an.

## Geschafft! ✨
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```
Es ist wichtig, gleichzeitig den Minus (-) Pin zu berühren, um eine Pin-Eingabe auszulösen. Halte den Calliope mini mit einer Hand am Minus (-) Pin fest und berühre mit einem Finger der anderen Hand einen der anderen Pins.
```


```template
//
```



