"TVShader" is a shader for Corona SDK that implements old-school style CRT effects.  It is intended for use when a full-screen effect is desired.  (It is not appropriate for filter-style use on non-full-screen areas.)

![](tvshader_beachballdemo.jpg)


#Basic Usage

Copy the TVShader.lua module into your project folder.  You may also copy it into a subdirectory of your project folder, though you'll need to account for that path in the sample code below.

Require the TVShader module within your code where it will be used.
```lua
local TVShader = require("TVShader")
```

Create two display groups - one to hold the original "contents" of your display, and one to hold the output from the effect.
```lua
local myContentGroup = display.newGroup()
local myOutputGroup = display.newGroup()
```

Create an instance of the shader, passing it references to the two groups:
```lua
local tvshader = TVShader({
  contentGroup = myContentGroup,
  outputGroup = myOutputGroup
})
```

That's basically it.

The effect will now be active, but only a bit of interference lines will be visible on the otherwise blank screen.

In order to actually _notice_ the effect it would help to have some actual content within the content group, even a simple square will do...
```lua
local rect = display.newRect( contentGroup,
  display.contentCenterX, display.contentCenterY,
  200, 200 )
```
![](tvshader_demo0docs.jpg)
