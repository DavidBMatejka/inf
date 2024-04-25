---
cssclasses:
  - clean-embeds
title: Turtle Klasse
tags:
  - AWT
  - Swing
publish: "true"
---
Die Aufgabe der Turtle Klasse ist es eine imaginäre Schildkröte zu simulieren (siehe auch: [Wikpedia: Turtle Graphics](https://en.wikipedia.org/wiki/Turtle_graphics)) Wenn sie sich vorwärts bewegt, soll sie einen Strich hinterlassen und sie kann mithilfe von Befehlen wie "goForward()" und "turnRight()" gesteuert werden.
In der Schule wird mit dem selben Prinzip anfangen zu Programmieren, indem man die Katze durch entsprechende Befehl dazu bringt, Figuren zu zeichnen.
![[scratchBeispiel.png]]

Die Turtle soll ihre und die letzte Koordinaten speichern, damit wir diese beide Punkte mit einer Linie verbinden können. Zusätzlich soll sie die folgenden Methoden besitzen:
- goForward(int length)
- turnLeft(int gradzahl)
- turnRight(int gradzahl)
Es können noch weitere Methoden definiert werden, aber diese drei reichen für eine einfache Turtle aus.
Für die Methode "goForward(int length)" müssen wir zusätzlich noch die aktuelle Richtung, in die die Turtle schaut, speichern. Dann können wir mithilfe von [Trigonometrie](https://de.wikipedia.org/wiki/Trigonometrie) die richtige Linie zeichnen.

>[!Aufgabe]
> 1. Implementiere eine Turtle-Klasse mit den gewünschten Methoden. Nutze dazu die untere Vorlage.

![[Turtle Vorlage]]
