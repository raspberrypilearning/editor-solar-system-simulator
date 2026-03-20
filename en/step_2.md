<h2 class="c-project-heading--task">Show Mercury orbit</h2>

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
line_highlights: 11-14,21-31,45
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
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])  # Draw Mercury's orbit ring using its orbit size


# draw_planets function


# load_planets function
def load_planets():
    global mercury  # Make mercury accessible outside this function

    mercury = {  # Store Mercury's data in a dictionary
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
    load_planets()  # Load Mercury before the first frame is drawn


def draw():
    # Put code to run every frame here
    background(0)
    no_stroke()
    draw_sun()
    draw_orbits()  # Draw Mercury's orbit ring each frame

def mouse_pressed():
    # Put code to run when the mouse is pressed here
    # Here the RGB value is converted to Hex so it can be used in a string comparison later
    pixel_colour = Color(get(mouse_x, mouse_y)).hex  # Read the colour of the pixel you clicked

    
run(frame_rate=60)
--- /code ---

</div>

<div class="c-project-callout c-project-callout--debug" style="font-size: 1.1em">
  <strong>Debug:</strong> If you get <code>NameError: name 'mercury' is not defined</code>, check you added both <code>global mercury</code> in <code>load_planets()</code> and the <code>load_planets()</code> line in <code>setup()</code>.
</div>

--- task ---
**Test:** Run your code and check you can see **one white orbit ring** around the Sun.
--- /task ---
