<h2 class="c-project-heading--task">Click Earth for facts</h2>

--- task ---
Add an Earth check so clicking Earth prints Earth’s name and fact.
--- /task ---

<div class="c-project-callout c-project-callout--tip" style="font-size: 1.1em">
  <strong>Tip:</strong> Using <code>elif</code> means only one planet’s fact prints per click.
</div>

<div class="c-project-code">

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 114
line_highlights: 125-127
---
def mouse_pressed():
    # Put code to run when the mouse is pressed here
    # Here the RGB value is converted to Hex so it can be used in a string comparison later
    pixel_colour = Color(get(mouse_x, mouse_y)).hex

    if pixel_colour == mercury['colour'].hex:
        print(mercury['name'])
        print(mercury['info'])
    elif pixel_colour == venus['colour'].hex:
        print(venus['name'])
        print(venus['info'])
    elif pixel_colour == earth['colour'].hex:
        print(earth['name'])
        print(earth['info'])


run(frame_rate=60)
--- /code ---

</div>

--- task ---
**Test:** Run your code and click Earth — check Earth’s **name and fact** print in the output.
--- /task ---
