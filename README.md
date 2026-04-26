import turtle
import math
import random


screen = turtle.Screen()
screen.bgcolor("black")
screen.title("Wazir HEART ART")

t = turtle.Turtle()
t.speed(0)
t.hideturtle()

COLOR = "#8B0000" 


def heart_coords(angle):
    x = 16 * math.sin(math.radians(angle))**3
    y = 13 * math.cos(math.radians(angle)) - 5 * math.cos(math.radians(2*angle)) - 2 * math.cos(math.radians(3*angle)) - math.cos(math.radians(4*angle))
    return x * 15, y * 15


def write_name():
    t.penup()
    t.goto(0, 250)  
    t.color(COLOR)  
    t.write(" Wazir", align="center", font=("Arial", 30, "bold"))
    
    
    t.goto(-100, 240)
    t.pendown()
    t.forward(200)
    t.penup()


write_name()


t.color(COLOR)
t.pensize(2)
t.penup()
for angle in range(12, 361):
    x, y = heart_coords(angle)
    t.goto(x, y)
    t.pendown()


t.pensize(0.5)
points = []
for angle in range(12, 361, 2):
    points.append(heart_coords(angle))

for _ in range(12):
    p1 = random.choice(points)
    p2 = random.choice(points)
    
    t.penup()
    t.goto(p1)
    t.pendown()
    t.color(COLOR)
    t.goto(p2)

turtle.done()
