---
tags:
  - lösung
publish: "true"
title: Lösung gesamt zu DrawingWithTurtle
---
```java
import javax.swing.*;
import java.awt.*;

public class DrawingWithTurtle extends JPanel {
    int depth;

    public DrawingWithTurtle(int depth) {
        this.depth = depth;
    }
    @Override
    public void paint(Graphics g) {
        Graphics2D g2d = (Graphics2D) g;

        Turtle turtle = new Turtle(0, getHeight() - 20, 0);
        turtle.setCanvas(g2d);

        zeichneKochkurve(turtle, getWidth() / 3.0, depth);
    }

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

    public static void main(String[] args) {
        int WIDTH = 800;
        int HEIGHT = 800;

        JFrame jFrame = new JFrame();
        jFrame.setSize(WIDTH, HEIGHT);
        jFrame.setBackground(Color.WHITE);
        jFrame.setDefaultCloseOperation(WindowConstants.EXIT_ON_CLOSE);
        jFrame.setVisible(true);

        jFrame.setLayout(new GridLayout(2, 2));

        for (int i = 0; i < 4; i++) {
            JPanel jPanel = new DrawingWithTurtle(i);
            jFrame.getContentPane().add(jPanel);
        }
    }
}
```