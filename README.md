# color-print
A simple function that allows you to print text with colors and formatting to terminal.

## Information
This package was originally created to allow me to to have more control over the colors shown in my cli's output. Colors that aren't supported by luvit's pretty-print theme.

## Installation
Using [lit](https://luvit.io/lit.html):
```
lit install TohruMKDM/color-print
```
Using [git](https://git-scm.com/):
```
git clone https://github.com/TohruMKDM/color-print.git
```

## Syntax
`[r,g,b;r,g,b](string)`
The first set of rgb values controls the foreground and the second set controls the background.
Values default to 0

## Documentation

#### `color_print.print(...)`
Takes a variable amount of arguments and writes them to stdout just like the standard print. The only difference is that it'll check each argument for the [syntax](https://github.com/TohruMKDM/color-print#syntax) and automatically convert them.</br>
Example: `color_print.print('Hello [red](Only this will be red) World!')`

#### `color_print.dump(value, escape, recursive)`
Primary use of this function is to dump table values to a human-readable string. If value is not a table then it behaves the same as tostring with the only difference being is that it will wrap string values in quotes.
Example: `color_print.dump('Hello World') -> 'Hello World'`<br/>
If `escape` is a truthy then it'll display the literal escape sequence<br/>
Example:
```lua
color_print.dump([[
Multi
Line
String
]], true)
-- '\nMulti\nLine\nString\n'
```
The `recursive` param is for as you've probably guessed, recursively dumping tables.

### `color_print.colorize(color, value)`
Returns value wrapped in the ANSI sequence that will give it color when written to stdout
Useful if you want to get a colorized string to manipulate rather than instantly outputting it. </br>
`color` may be a registered color or a string that allows `r, g, b` </br>
Example: `color_print.colorize('red', 'Red String') -> \027[38;2;255;0;0mRed String\027[0m`

### `color_print.colorize:setColor(name, value)`
Registers a color to be used in the colorizer</br>
Example: `color_print.colorize:setColor('yellow', '254, 221, 0')`</br>
Now `color_print.print('[yellow](Yellow String)')` prints yellow text to terminal

## Example
```lua
local color_print = require('color-print')

-- Print a red 'Hello World!' to stdout.
color_print.print('[255,0,0](Hello World!)')

-- Default values, this does the same thing as the previous call.
color_print.print('[255](Hello World!)')

-- If you want to only set the background color then pass '-' to the foreground.
-- Prints 'Hello World!' to stdout with a red background.
color_print.print('[-;255,0,0](Hello World!)')

-- Prints a red colored 'Hello World' with a green background to stdout.
color_print.print('[255,0,0;0,255,0](Hello World!)')

-- 2.0
-- Colors red, green, and blue are pre-set.
color_print.print('[red](This text will be red)')
color_print.print('[green](This text will be green)')
color_print.print()
```