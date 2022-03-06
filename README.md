# color-print
A simple function that allows you to print text with colors to terminal.
## Installation
Using [lit](https://luvit.io/lit.html):
```
lit install TohruMKDM/color-print
```
Using [git](https://git-scm.com/):
```
https://github.com/TohruMKDM/color-print.git
```
## Syntax
`[r,g,b;r,g,b](string)`
The first set of rgb values controls the foreground and the second set controls the background.
Values default to 0
## Example
```lua
local cp = require('color-print')

-- Print a red 'Hello World!' to stdout.
cp('[255,0,0](Hello World)!')

-- Default values, this does the same thing as the previous call.
cp('[255](Hello World!)')

-- If you want to only set the background color then pass '-' to the foreground.
-- Prints 'Hello World!' to stdout with a red background.
cp('[-;255,0,0](Hello World!)')

-- Prints a red colored 'Hello World' with a green background to stdout.
cp('[255,0,0;0,255,0](Hello World!)')
```