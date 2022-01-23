# mkxp extenions for Dancing Dragon Games / Symphony of War

## Graphics.resize_window(width, height, recenter)
width: Integer  
height: Integer  
recenter: Boolean, false by default  
returns: nil  

Resizes the game window to width x height. If `recenter` is **true**, also center the window on the current screen.

## Bitmap.write_to_png(filename)
filename: String  
returns: self  

Writes the contents of the bitmap to `filename`, in PNG format.

## Input.scroll_v()
returns: Integer  

Returns the cumulative amount of scroll events (negative if down, positive if up) inbetween the current and last `Input.update` call.

## Input::MOUSEX1 / ::MOUSEX2

These two constants representing two extra mouse buttons can be passed to the familiar #press?/#trigger?/#repeat? functions.

## MKXP.data_directory()
returns: String  

Provides a PC-user-dependant, game-specific path to a writable directory, intended for save states, configuration and similar.
In `mkxp.conf`, both `dataPathOrg` and `dataPathApp` keys need to be set, otherwise it returns a generic directory shared by all mkxp games. It is recommended (though not required) to not put any spaces in the config strings.  
Real life example:  
```
dataPathOrg=dancingdragon
dataPathApp=skyborn
```

## Arbitrary key states
Use `MKXP.raw_key_states` to get the current byte array of keystates, then call `#getbyte(scancode)` with `scancode` being one of the constants defined in `SDL_scancode_map.rb`. **0** means the key is released, **1** that it is pressed.
