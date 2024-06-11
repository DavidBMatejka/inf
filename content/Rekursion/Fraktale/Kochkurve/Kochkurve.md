---
title: Kochkurve
publish: "true"
cssclasses:
  - clean-embeds
tags:
  - rekursion
  - fraktal
---
![[KochkurveTiefe4.png]]

---
Oben ist ein selbstähnliches Fraktal[^1] zu sehen, welches als Kochkurve bezeichnet wird. Mithilfe von Rekursion ist es überraschend einfach diese zeichnen zu lassen. Wir verwenden dazu eine Turtle-Klasse mit der wir eine imaginäre Schildkröte über den Bildschirm bewegen können, die während sie läuft einen Strich zeichnet.

### Zeichnen lernen

>[!faq] Aufgabe
>1. Erstelle ein Programm um Linien zeichnen zu können: [[In Java zeichnen - Drawing with Turtle]]
>2. Erstelle die [[Turtle Klasse]].
> 3. Probiere die Turtle-Klasse aus, indem du beliebige Figuren zeichnest, wie Vierecke, Dreiecke, ...

### Kochkurve zeichnen

>[!faq] Aufgabe
>1. Vervollständige in der [[In Java zeichnen - Drawing with Turtle|DrawingWithTurtle]]-Klasse die Methode `zeichneKochkurve(Turtle turtle, double length, int depth)`. Die Methode soll erst einmal nur die folgende Kurve zeichnen:
>![[KochKurveSchritt1.png]]
>2. Vervollständige die Methode, sodass die Kochkurven mit beliebiger Tiefe gezeichnet werden können.

>[!tip]- Tipps
> - Überlege dir um wie viel Grad sich die Turtle jeweils drehen muss. Eine Skizze auf Papier kann ebenfalls helfen.
> - Zur Aufgabe Teil 2: Teil 1 bildet die Rekursionsbasis. Für eine Kochkurve der Tiefe $n$, soll anstatt einer gerade Linie wiederum eine Kochkurve, jedoch mit Tiefe $n-1$ gezeichnet werden.

Wurde die `zeichneKochkurve(...)`-Methode erfolgreich implementiert, dann sollten die ersten vier Kochkurven mit Rekursionstiefen 0 bis 3 so aussehen:
![[KochKurveIteration1-4.png]]
>[!done]- Lösung
>  ![[Lösung zur Methode zeichneKochkurve()]]
>  [[Lösung gesamt zu DrawingWithTurtle]]


---

>[!faq] Zusatzaufgabe 
> Hat man die Kochkurve programmiert, lässt sie sich mit wenig Aufwand zur Koch'schen Schneeflocke erweitern:  ![[Kochsche Schneeflocke.png]]

> [!done]- Lösung
> ![[Lösung Kochsche Schneeflocke]]


---
[^1]: https://de.wikipedia.org/wiki/Fraktal