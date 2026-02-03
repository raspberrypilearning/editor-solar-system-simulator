<h2 class="c-project-heading--task">Click Venus for facts</h2>

--- task ---
Add a Venus check so clicking Venus prints Venus’s name and fact.
--- /task ---

<div class="c-project-callout c-project-callout--debug" style="font-size: 1.1em">
  <strong>Debug:</strong> If clicking does nothing, make sure you used <code>==</code> for comparison (not <code>=</code>).
</div>

<div class="c-project-code">

--- code ---
---
language: python
filename: main.py
line_numbers: true
line_number_start: 91
line_highlights: 99-101
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


run(frame_rate=60)
--- /code ---

</div>

--- task ---
**Test:** Run your code and click Venus — check Venus’s **name and fact** print in the output.
--- /task ---
