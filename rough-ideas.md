# Rough Ideas  
These are a rough set of fields in the `.bimg` format.  

# Image data
A line is a tuple of (text, text colors, background colors) in blit format.  
Frames are lists of lines.  
Image files may be a single frame, or list of frames.  
Each frame can have a `palette` key to specify a specific palette for that frame, following the rules of the base `palette` key.
  
# Metadata
Metadata is stored at the root of the table.    
`version`: string Version string of the format.  
`animation`: boolean Whether the image is an animation (if so, each frame is numerically indexed).  
(per frame) `duration`: number Duration of the frame in seconds, overrides `secondsPerFrame` for that frame.  
`secondsPerFrame`: number Default length of each frame in seconds.  
`palette`: table Palette table in format of colors api (key: color number - value: EITHER table of 3 ranged 0-1 floats for each RGB component, OR a single item which is the hex-formatted number #RRGGBB). This will serve as the starting palette for any animations or images.   
(per frame) `palette`: table Per frame palette, set before drawing the frame. Same format as the root `palette`.

`title`: string Original title of the image.  
`description`: Long form description of the file.  
`author`: Author of the image.  
`creator`: Software used to create the image.  
`date`: Date the image was created in ISO-8601 format.  
