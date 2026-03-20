<h2 class="c-project-heading--task">Add Earth</h2>

--- task ---

Load Earth from <code>planets.csv</code> and draw Earth so you can see three planets orbiting.

--- /task ---

<div class="c-project-code">

--- code ---

---
language: python
filename: main.py
line_numbers: true
line_number_start: 10
line_highlights: 16,44-55,85-93
---
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)  # Make it white
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
    ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])
    ellipse(width / 2, height / 2, earth['orbit'], earth['orbit'])  # Draw Earth's orbit ring

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

    colour = venus['colour']
    orbit = venus['orbit']
    size = venus['size']
    speed = venus['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

    # Draw Earth
    colour = earth['colour']  # Get Earth's colour from the dictionary
    orbit = earth['orbit']  # Get Earth's orbit diameter
    size = earth['size']  # Get Earth's drawn size
    speed = earth['speed']  # Get Earth's orbit speed

    make_planet(  # Draw Earth moving around its orbit
        colour,
        orbit,
        size,
        speed
    )


# load_planets function
def load_planets():
    global mercury, venus, earth  # Make all three planet dictionaries global

    mercury = {
        'name': 'Mercury',
        'colour': Color(165, 42, 42),
        'size': 15,
        'orbit': 150,
        'speed': 1,
        'info': 'The smallest, and fastest, planet.'
    }

    with open('planets.csv') as f:
        data = f.read()
        lines = data.splitlines()

    planet = lines[2].split(',')  # Split Venus' data
    venus = {
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),  # int() for whole numbers
        'orbit': int(planet[5]),
        'speed': float(planet[6]),  # float() for decimals
        'info': planet[7]
    }

    planet = lines[3].split(',')  # Split Earth's data from the CSV line
    earth = {  # Build Earth's dictionary from the CSV values
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),
        'orbit': int(planet[5]),
        'speed': float(planet[6]),
        'info': planet[7]
    }

--- /code ---

</div>

--- task ---

**Test:** Run your code and check you can see **three orbit rings** and **three planets** moving.

--- /task ---


<div class="c-project-callout c-project-callout--debug" style="font-size: 1.1em">
  <strong>Debug:</strong> If you get an “index out of range” error, open <code>planets.csv</code> and check Earth is on the line your code is using.
</div>
