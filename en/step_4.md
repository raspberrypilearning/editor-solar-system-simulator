<h2 class="c-project-heading--task">Add Venus</h2>

### Step 1
Load Venus from <code>planets.csv</code> and draw Venus so you can see two planets orbiting.

<div class="c-project-callout c-project-callout--tip" style="font-size: 1.1em">
  <strong>Tip:</strong> CSV data is read as text, so you use <code>int()</code> and <code>float()</code> to convert number strings to number **values**.
</div>

<div class="c-project-code">

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 10
line_highlights: 15,31-41,45,57-69
---
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)  # Make it white
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
    ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])

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

# load_planets function
def load_planets():
    global mercury, venus

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

    planet = lines[2].split(',')
    venus = {
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),
        'orbit': int(planet[5]),
        'speed': float(planet[6]),
        'info': planet[7]
    }
--- /code ---

</div>

### Step 2
**Test:** Run your code and check you can see **two orbit rings** and **two planets** moving.
