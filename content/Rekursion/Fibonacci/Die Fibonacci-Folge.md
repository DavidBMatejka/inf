---
tags:
  - rekursion
title: Die Fibonacci-Folge
publish: "true"
---
Die Fibonacci-[[Folgen|Folge]][^1]  ($0,1,1,2,3,5,8,13,$...) hat eine leicht zu erkennende rekursive Definition, denn ein Folgenglied lässt sich aus Addition der beiden vorherigen berechnen. Die explizite dagegen ist nicht offensichtlich.

| Fibonacci    | Vorschrift                                                                                                                       |
| ------------ | -------------------------------------------------------------------------------------------------------------------------------- |
| **rekursiv** | $a_n = a_{n-2} + a_{n-1}\,$, $a_0 = 0$, $a_1=1$                                                                                  |
| **explizit** | $a_n = \frac{1}{\sqrt{5}}\left( \left( \frac{1+\sqrt{5}}{2} \right)^n - \left(\frac{1-\sqrt{5}}{2}\right)^n  \right)$, $n \geq0$ |
## Rekursive Implementierung
Die Fibonacci-Folge lässt sich auch in Java sehr leicht rekursiv implementieren.
```java
public long fib(int n) {
    if (n == 0) return 1;
    if (n == 1) return 1;

	return fib(n - 2) + fib(n - 1);
}
```

### Laufzeit-Problem
Diese Implementierung hat jedoch den Nachteil, dass mehrfach das gleiche Folgenglied ausgerechnet wird. Im folgenden Bild sieht man die Rekursionsaufrufe für `fib(10)` für eine Rekursionstiefe von 3. Die Aufrufe gehen weiter bis `fib(0)` oder `fib(1)` erreicht wurde.
![[FibonacciRecursionCall.png]]
Durch die wiederkehrende Aufteilung in zwei fast gleich große Subprobleme, ist die Laufzeit exponentiell mit $O(2^n)$[^2][^3]. 

### Lösung des Laufzeitproblems
Um dieses Problem zu lösen, müssen wir die Zwischenergebnisse speichern, damit diese nicht erneut berechnet werden, sondern abgerufen werden können. Diese Methode wird als "Dynamische Programmierung" [^4] bezeichnet.
Hier ist eine rekursive Lösung mit Speicherung der Zwischenergebnisse:

```java
    public static long betterFib(int n, List<Long> values) {
        if (n < values.size()) return values.get(n);

        if (n == 0) {
            values.addFirst(0L);
            return 0;
        }
        if (n == 1) {
            values.add(1, 1L);
            return 1;
        }

        values.add(n, betterFib(n - 2, values) + betterFib(n - 1, values));
        return values.get(n);
    }
```

Wird Rekursion und das Speichern von Zwischenergebnissen kombiniert, spricht man auch von Memoisation[^5].

## Iterative Implementierung
Eine iterative Implementierung löst dieses Problem automatisch:

```java
public static long fibIterative(int n) {
	long a = 0;
	long b = 1;

	for (int i = 0; i < n; i++) {
		long tmp = a + b;
		a = b;
		b = tmp;
	}
	return a;
}
```
Worin besteht nun also der Vorteil einer Rekursion, wenn sowohl die Implementierung einfach ist und die Laufzeit direkt linear ist mit $O(n)$.

## Explizite Implementierung
Implementiert man die explizite Formel, ergibt sich eine Funktion mit konstanter Laufzeit $O(1)$. 

```java
public static long fibExplicit(int n) {
	return (long) ((1.0 / Math.sqrt(5)) * (
				Math.pow((1 + Math.sqrt(5)) / 2.0, n)
				- Math.pow((1 - Math.sqrt(5)) / 2.0, n)
				)
	);
}
```
Die explizite Formel hat in der Programmierung jedoch das Problem, dass zum Beispiel die $\sqrt5$ nur näherungsweise bestimmt werden kann, da wir keine unendliche Anzahl nach Nachkommastellen speichern können.

## Das 93.te Folgeglied von Fibonacci
Die Folgenglieder übersteigen sehr schnell den Bereich von `int` oder auch `long`. Das letzte Folgenglied, das noch in den `long` Bereich fällt ist $n=92$, sodass man die Klasse `BigInteger` benutzen muss, um `fib(93)` und aufwärts ausrechnen zu können. Dabei ist die iterative Implementierung leichter angepasst, als die explizite, da die iterative Lösung nur die Addition verwendet und wir uns nicht überlegen müssen wie wir mit $\sqrt5$ umgehen.

```java
public static BigInteger fibIterativeBig(int n) {
	BigInteger a = new BigInteger("0");
	BigInteger b = new BigInteger("1");

	for (int i = 0; i < n; i++) {
		BigInteger tmp = a.add(b);
		a = b;
		b = tmp;
	}
	return a;
}
```


[^1]: https://de.wikipedia.org/wiki/Fibonacci-Folge
[^2]: https://www.studysmarter.co.uk/explanations/computer-science/algorithms-in-computer-science/fibonacci-algorithm/
[^3]: https://www.baeldung.com/cs/fibonacci-computational-complexity
[^4]: https://de.wikipedia.org/wiki/Dynamische_Programmierung
[^5]: https://www.geeksforgeeks.org/what-is-memoization-a-complete-tutorial/