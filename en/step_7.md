## Add Earth facts

Add an Earth check so clicking Earth prints Earth’s name and fact.

> [!TIP]
>
> Using `elif` means only one planet’s fact prints per click.

```python filename="main.py" line_numbers="true" line_number_start="107" line_highlights="118-120"
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
```

## Now run your code

Click Earth — check Earth’s **name and fact** print in the output.
