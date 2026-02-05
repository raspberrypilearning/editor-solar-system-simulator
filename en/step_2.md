<h2 class="c-project-heading--task">Show Mercury’s orbit</h2>

--- task ---
Create a Mercury dictionary and use it to draw a white orbit ring around the Sun.
--- /task ---

<div class="c-project-callout c-project-callout--tip" style="font-size: 1.1em">
  <strong>Tip:</strong> You can fetch a value from a dictionary using square brackets, like <code>mercury['orbit']</code>.
</div>

<div class="c-project-code">

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 10-14,20-31,37,45
---
from p5 import *
from make_planet import make_planet


def draw_sun():
    fill(255, 255, 0)  # Yellow
    ellipse(width / 2, height / 2, 100, 100)


# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)  # Make it white
    
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])


# draw_planets function


# load_planets function
def load_planets():
    global mercury

    mercury = {
        'name': 'Mercury',
        'colour': Color(165, 42, 42),
        'size': 15,
        'orbit': 150,
        'speed': 1,
        'info': 'The smallest, and fastest, planet.'
    }


def setup():
    # Put code to run once here
    size(400, 400)
    load_planets()


def draw():
    # Put code to run every frame here
    background(0)
    no_stroke()
    draw_sun()
    draw_orbits()

def mouse_pressed():
    # Put code to run when the mouse is pressed here
    # Here the RGB value is converted to Hex so it can be used in a string comparison later
    pixel_colour = Color(get(mouse_x, mouse_y)).hex

    
run(frame_rate=60)
--- /code ---

</div>

--- task ---
**Test:** Run your code and check you can see **one white orbit ring** around the Sun.
--- /task ---
