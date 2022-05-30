# Rough Ideas  
These are a rough set of fields in the `.bimg` format.  

# Image data
A line is a tuple of (text, text colors, background colors) in blit format.  
Frames are lists of lines.  
Image files may be a single frame, or list of frames.  
  
# Metadata
Metadata is stored at the root of the table.    
`version`: string Version string of the format.  
`animation`: boolean Whether the image is an animation (if so, each frame is numerically indexed).  
(per frame) `duration`: number Duration of the frame in seconds, overrides `secondsPerFrame` for that frame.  
`secondsPerFrame`: number Default length of each frame in seconds.  
`palette`: table Table of palette colors. In format of [colors api](https://tweaked.cc/module/colors.html) (key: color number - value: RGB float table OR 24bit color integer (#0xRRGGBB))  

`title`: string Original title of the image.  
`description`: Long form description of the file.  
`author`: Author of the image.  
`creator`: Software used to create the image.  
`date`: Date the image was created in ISO-8601 format.  
