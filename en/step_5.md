<h2 class="c-project-heading--task">Add Venus</h2>

--- task ---
Load Venus from <code>planets.csv</code> and draw Venus so you can see two planets orbiting.
--- /task ---

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
line_highlights: 15,32-43,57-69
---
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)  # Make it white
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
    ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])  # Draw Venus' orbit ring

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

    # Draw Venus
    colour = venus['colour']  # Get Venus' colour from the dictionary
    orbit = venus['orbit']  # Get Venus' orbit diameter
    size = venus['size']  # Get Venus' drawn size
    speed = venus['speed']  # Get Venus' orbit speed

    make_planet(  # Draw Venus moving around its orbit
        colour,
        orbit,
        size,
        speed
    )

# load_planets function
def load_planets():
    global mercury, venus  # Make both planet dictionaries global

    mercury = {
        'name': 'Mercury',
        'colour': Color(165, 42, 42),
        'size': 15,
        'orbit': 150,
        'speed': 1,
        'info': 'The smallest, and fastest, planet.'
    }

    with open('planets.csv') as f:  # Load Venus from planets.csv
        data = f.read()  # Read the whole file into a string
        lines = data.splitlines()  # Split into a list of lines (one per planet)

    planet = lines[2].split(',')  # Split Venus' data into a list of values
    venus = {  # Build Venus' dictionary from the CSV values
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),  # int() for whole numbers
        'orbit': int(planet[5]),
        'speed': float(planet[6]),  # float() for decimals
        'info': planet[7]
    }
--- /code ---

</div>

--- task ---
**Test:** Run your code and check you can see **two orbit rings** and **two planets** moving.
--- /task ---
