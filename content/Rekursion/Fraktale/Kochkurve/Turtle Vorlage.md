---
tags:
  - vorlage
publish: "true"
---
```java
import java.awt.*;

public class Turtle {
    private double x, y, oldx, oldy;
    private double angle;

    // canvas for the turtle to draw on
    private Graphics2D g2d;

    public Turtle(double x, double y, double dir) {
        this.x = x;
        this.y = y;
        angle = dir;
    }

    public void turnLeft(double delta) {
        angle -= delta;
    }
    public void turnRight(double delta) {
        angle += delta;
    }

    public void goForward(double step) {
        oldx = x;
        oldy = y;
        x += //todo 
        y += //todo
        draw(g2d);
    }

    private void draw(Graphics2D g2d) {
        g2d.drawLine((int) oldx, (int) oldy, (int) x, (int) y);
    }

    // tells the turtle where to draw
    public void setCanvas(Graphics2D g2d) {
        this.g2d = g2d;
    }
}

```