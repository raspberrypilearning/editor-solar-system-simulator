## Add Venus facts

Add a Venus check so clicking Venus prints Venus’s name and fact.

```python filename="main.py" line_numbers="true" line_number_start="85" line_highlights="93-95"
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
```

## Now run your code

Click Venus — check Venus’s **name and fact** print in the output.

> [!DEBUG]
>
> If clicking does nothing, make sure you used `==` for comparison (not `=`).
