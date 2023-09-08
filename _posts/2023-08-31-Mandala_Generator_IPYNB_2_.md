---
toc: True
comments: True
layout: default
title: Mandala Generator
description: A turtle based mandala generator
type: hacks
courses: {'compsci': {'week': 2}}
---

# Python Mandal Generator


Inspired by my Drawing and Painting 1 Class in which we're currently making mandalas.

Runs using turtle.Pen() and runs in randomized circle radii and angles which gradually changing color as loop progresses.

Probably the only thing wrong about this project is that it's not made up of concentric circles.

Dependencies:
- Python (any version)
- turtle (any version)


```python
# import turtle
import turtle
import random

# defining colors
colors = ['red', 'yellow', 'green', 'purple', 'blue', 'orange']

# setup turtle pen
t= turtle.Pen()

# changes the speed of the turtle
t.speed(10)

# changes the background color
turtle.bgcolor("black")

# make spiral_web
for x in range(200):
	t.pencolor(colors[x%6]) # setting color
	t.width(x/100 + 1) # setting width
	t.forward(x) # moving forward
	t.left(random.randint(40,80)) # moving left

turtle.done()
```

## Sample Output Mandala:
<img src="/student/images/mandala.png">
