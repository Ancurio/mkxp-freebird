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

## Arbitrary key states
Use `MKXP.raw_key_states` to get the current byte array of keystates, then call `#getbyte(scancode)` with `scancode` being one of the constants defined in `SDL_scancode_map.rb`. **0** means the key is released, **1** that it is pressed.
