<h2 class="c-project-heading--task">Add Mercury facts</h2>

--- task ---
Detect when Mercury is clicked and print its name and fact in the output.
--- /task ---

<div class="c-project-callout c-project-callout--tip" style="font-size: 1.1em">
  <strong>Tip:</strong> Your code checks the colour of the pixel you clicked — so you need to click on the planet itself.
</div>

<div class="c-project-code">

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 48
line_highlights: 62-64
---
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

    if pixel_colour == mercury['colour'].hex:  # Check if the clicked pixel matches Mercury's colour
        print(mercury['name'])  # Print Mercury's name
        print(mercury['info'])  # Print Mercury's fact


run(frame_rate=60)
--- /code ---

</div>

--- task ---
**Test:** Run your code and click Mercury — check Mercury’s **name and fact** print in the output.
--- /task ---
