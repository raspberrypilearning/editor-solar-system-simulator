<h2 class="c-project-heading--task">Make Mercury</h2>

--- task ---
Use Mercury’s dictionary to draw Mercury so you can see it moving around the orbit.
--- /task ---

<div class="c-project-callout c-project-callout--debug" style="font-size: 1.1em">
  <strong>Debug:</strong> If you get an error about <code>make_planet</code>, check <code>make_planet.py</code> is in your project and the import line is still at the top of <code>main.py</code>.
</div>

<div class="c-project-code">

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 1
line_highlights: 20,22-25,27-32,61
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
def draw_planets():

    colour = mercury['colour']
    orbit = mercury['orbit']
    size = mercury['size']
    speed = mercury['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )


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
    draw_planets()

def mouse_pressed():
    # Put code to run when the mouse is pressed here
    # Here the RGB value is converted to Hex so it can be used in a string comparison later
    pixel_colour = Color(get(mouse_x, mouse_y)).hex

    
run(frame_rate=60)
--- /code ---

</div>

--- task ---
**Test:** Run your code and check you can see **Mercury moving** around the orbit ring.
--- /task ---
