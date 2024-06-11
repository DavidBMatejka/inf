---
cssclasses:
  - clean-embeds
title: Permutationen
tags:
  - rekursion
publish: "true"
---
## Permutationen
Es sollen alle [[Permutation]] für n Elemente erzeugt werden. Das heißt für einen Text $ABC$, welcher aus den Elementen $A$, $B$, $C$ besteht, wären das $ABC$, $ACB$, $BAC$, $BCA$, $CAB$, $CBA$

### Iterativ
#todo

>[!faq] Aufgabe
>Implementiere eine iterative Funktion, die für $n$ Elemente alle Permutationen als Liste zurückgibt.

#### Iterative Lösung
#todo 

Hier ist die iterative Lösung nicht so offensichtlich wie bei der Fakultät. Eine rekursive Lösung ist hier für manche vielleicht einfacher. 

#### **Erarbeitung - rekursive Lösung**
Wir schauen uns die möglichen Permutationen genauer an:

$ABC$,
$ACB$,
$BAC$,
$BCA$,
$CAB$,
$CBA$

Wir sehen, dass jeder einzelne Buchstabe des Texts einmal ganz vorne steht und dann die restlichen beiden dahinter. $BC$ und $CB$ sind die Permutationen für die zwei Elemente $B$ und $C$. Wir können also jeden Buchstaben einmal ganz vorne hinschreiben und dann auf den Rest wiederum die Permutationen aufschreiben. 
Wie bei Fibonacci müssen wir die Rekursionsbasis angeben, um einen Endlosaufruf der Permutations-Funktion zu verhindern. Wenn Die Länge des Textes nur $1$ beträgt, können wir den einzelnen Buchstaben zurückgeben.

>[!faq] Aufgabe
>1. Schreibe einen Pseudocode zur Berechnung aller Permutationen für einen Text aus $n$-vielen Buchstaben.
>2. Implementiere den Algorithmus in Java. 
>3. Bestimme die Laufzeit.
 
 >[!hint]-  Tipps
 > - Tipp: Wenn du nicht weißt, wie du starten sollst, dann spiele einmal das Vorgehen auf Papier durch.

>[!done]- Lösungen
> 1. [[Permutationen Pseudocode Lösung]]  
> 2. [[Permutationen Java]]
> 3. $O(n^2)$
> 
> Siehe auch:
> 
> https://de.wikipedia.org/wiki/Heap-Algorithmus
> https://de.wikipedia.org/wiki/Steinhaus-Johnson-Trotter-Algorithmus
> https://www.geeksforgeeks.org/print-all-permutations-of-a-string-in-java/
