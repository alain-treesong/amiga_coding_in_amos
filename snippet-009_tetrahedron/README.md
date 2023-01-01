## Rotating tetrahedron

To complete the 3D examples, here is a solid surface tetrahedron rotating on two axes.

![Solid tetrahedron](readImg/tetrahedron.png)

### Determining the sides to be drawn

The difference with the previous examples is that here we have to determine the sides to be drawn.
Many algorithms exist. As a tetrahedron is convex, it is possible to simply use the scalar product to determine whether a side should be drawn or not.
So once the 3D coordinates are projected, the scalar product is calculated on two 2D segments defining a side. Depending on the sign, the side is drawn or not.

### How it works

A screen of two bitplanes is opened. 
The tetrahedron is made of 4 points (x,y,z coords) centered on the origin :
```
Data 1,1,1
Data -1,-1,1
Data -1,1,-1
Data 1,-1,-1
```

A variant of the "Turbo draw" instruction is used:
Turbo Draw x1,y1 To x2,y2,c,bitplanes

x1,y1,x2 and y2 are the coordinates of the segment to be drawn.
The parameter c is the index of the colour to be used.
The parameter bitplanes indicates the bitplanes to be filled. If the value is negative, a special plotting mode is used so that the filling can be done with the "Blitter Fill" command.
The Amiga's blitter allows to draw segments and fill surfaces. These two instructions are provided by the Amcaf extension that is installed with the Amos 2020.1 community version. More information on these two instructions can be found in the detailed Amcaf documentation (available on Aminet)

### It can be optimized (of course !)

You get about (a bit more) than 25 fps on a standard A500 with this snippet.
But you can of course get 50 fps (keeping the realtime) by replacing arrays by simple variables and by using the fact that coordinates of this tetrahedron are only 1 or -1

An optimized version of this code can be seen in the demo "Merry and Happy" : https://www.youtube.com/watch?v=TphZpjZTTAc&ab_channel=AlainTreesong

