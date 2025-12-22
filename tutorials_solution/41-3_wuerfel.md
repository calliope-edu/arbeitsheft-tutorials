# 41 3_Würfel

```package
v3
```

## Aufgabe @showdialog
Verwandle den Calliope mini in einen Würfel.
Wird der Calliope mini geschüttelt, lasse eine zufällige Zahl auf der LED-Matrix erscheinen.
![](https://calliope.cc/tutorials/dice_animation.gif)


## Eingabe definieren
Wähle als Eingabe den Block ``||input.wenn geschüttelt||``.

```blocks
input.onGesture(Gesture.Shake, function () {

})
```

## Ausgabe definieren
Verwende den ``||basic.zeige Zahl||``-Block, um dir im ersten Schritt eine beliebige Zahl auszugeben.

```blocks
input.onGesture(Gesture.Shake, function () {
basic.showNumber(0)
})
```

## Zufall hinzufügen
Ersetze die Zahl durch den ``||math.wähle eine zufällige Zahl||`` Block, und stelle den Zahlenraum `1 bis 6` ein.

```blocks
input.onGesture(Gesture.Shake, function () {
basic.showNumber(randint(1, 6))
})
```

## Geschafft! 😍
Klicke auf ``|Herunterladen|``, um dein Programm auf deinen Calliope mini zu übertragen.

```template
//
```




