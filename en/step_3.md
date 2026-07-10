## Add Mercury facts

Detect when Mercury is clicked and print its name and fact in the output.

> [!TIP]
>
> Your code checks the colour of the pixel you clicked — so you need to click on the planet itself.

```python filename="main.py" line_numbers="true" line_number_start="49" line_highlights="62-64"
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

    if pixel_colour == mercury['colour'].hex:
        print(mercury['name'])
        print(mercury['info'])


run(frame_rate=60)
```

## Now run your code

Click Mercury — check Mercury’s **name and fact** print in the output.
