---
title: Lösung Kochkurve
tags:
  - lösung
publish: "true"
---
```java
public void zeichneKochkurve(Turtle turtle, double length, int depth) {
	if (depth == 0) {
		turtle.goForward(length);
		turtle.turnLeft(60);
		turtle.goForward(length);
		turtle.turnRight(120);
		turtle.goForward(length);
		turtle.turnLeft(60);
		turtle.goForward(length);
		return;
	}

	zeichneKochkurve(turtle, length / 3.0, depth - 1);
	turtle.turnLeft(60);
	zeichneKochkurve(turtle, length / 3.0, depth - 1);
	turtle.turnRight(120);
	zeichneKochkurve(turtle, length / 3.0, depth - 1);
	turtle.turnLeft(60);
	zeichneKochkurve(turtle, length / 3.0, depth - 1);
}
```