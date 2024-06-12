---
publish: "true"
tags:
  - fraktal
  - lösung
  - rekursion
---


```java
public void zeichneSierpinski(Turtle turtle, double length, int depth) {
	if (depth == 0) {
		return;
	}
	
	turtle.goForward(length);
	zeichneSierpinski(turtle, length / 2, depth - 1);
	turtle.goForward(length);
	turtle.turnLeft(120);
	turtle.goForward(length);
	zeichneSierpinski(turtle, length / 2, depth - 1);
	turtle.goForward(length);
	turtle.turnLeft(120);
	turtle.goForward(length);
	zeichneSierpinski(turtle, length / 2, depth - 1);
	turtle.goForward(length);
	turtle.turnLeft(120);
}
```