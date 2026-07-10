## Add Earth

Load Earth from `planets.csv` and draw Earth so you can see three planets orbiting.

```python filename="main.py" line_numbers="true" line_number_start="10" line_highlights="16,44-54,58,83-91"
# draw_orbits function
def draw_orbits():
    no_fill()
    stroke(255)  # Make it white
    ellipse(width / 2, height / 2, mercury['orbit'], mercury['orbit'])
    ellipse(width / 2, height / 2, venus['orbit'], venus['orbit'])
    ellipse(width / 2, height / 2, earth['orbit'], earth['orbit'])

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

    colour = earth['colour']
    orbit = earth['orbit']
    size = earth['size']
    speed = earth['speed']

    make_planet(
        colour,
        orbit,
        size,
        speed
    )

# load_planets function
def load_planets():
    global mercury, venus, earth

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

    planet = lines[3].split(',')
    earth = {
        'name': planet[0],
        'colour': Color(int(planet[1]), int(planet[2]), int(planet[3])),
        'size': int(planet[4]),
        'orbit': int(planet[5]),
        'speed': float(planet[6]),
        'info': planet[7]
    }
```

## Now run your code

Check you can see **three orbit rings** and **three planets** moving.

> [!DEBUG]
>
> If you get an “index out of range” error, open `planets.csv` and check Earth is on the line your code is using.
