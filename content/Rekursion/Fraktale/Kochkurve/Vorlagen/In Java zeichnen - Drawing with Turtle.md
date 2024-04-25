---
title: In Java zeichnen
publish: "true"
tags:
  - AWT
  - Swing
aliases:
  - DrawingWithTurtle
---
Diese Vorlage zeichnet vorerst eine einzelne Linie.

```java
import javax.swing.*;
import java.awt.*;

public class DrawingWithTurtle extends JPanel {

    @Override
    public void paint(Graphics g) {
        Graphics2D g2d = (Graphics2D) g;

        g2d.drawLine(0, 0, 100, 100);

    // uncomment this if turtle is implemented and delete the drawLine above
    /*
        Turtle turtle = new Turtle(0, getHeight() - 20, 0);
        turtle.setCanvas(g2d);

        turtle.goForward(100);
        turtle.turnLeft(90);
        turtle.goForward(100);
    */

    }

    public void zeichneKochkurve(Turtle turtle, double length, int depth) {
        //todo
    }

    public static void main(String[] args) {
        int WIDTH = 800;
        int HEIGHT = 800;

        JFrame jFrame = new JFrame();
        jFrame.setSize(WIDTH, HEIGHT);
        jFrame.setBackground(Color.WHITE);
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        jFrame.setVisible(true);

        JPanel jPanel = new DrawingWithTurtle();
        jFrame.getContentPane().add(jPanel);
    }
}
```

---
### Weitere Infos
Die beiden gebräuclichen Bibliotheken, um in Java Graphische Oberflächen (GUIs) zu erstellen, sind Swing/AWT und JavaFX.
Swing/AWT kommt direkt mit den JavaJDKs gebündelt und benötigt deshalb keine Installation, wie das bei JavaFX der Fall ist.
Deshalb wird im [[Kochkurve]]-Abschnitt Swing/AWT verwendet, um den Overhead möglichst gering zu halten.

In vielen Beispielen wird die Klasse mit `extends JFrame` erweitert. Online konnte ich keine offizielle Variante finden, aber habe mich für das obige Template aus folgendem Grund entschieden.

> Avoid extending JFrame as it ties your GUI to being, well a JFrame. If instead you concentrate on creating JPanels instead, then you have the freedom to use these JPanels anywhere needed -- in a JFrame, or JDialog, or JApplet, or inside of another JPanel, or swapped with other JPanels via a CardLayout.

\- Quelle: [Extending JFrame vs. Creating inside program](https://stackoverflow.com/questions/22003802/extends-jframe-vs-creating-it-inside-the-program)

