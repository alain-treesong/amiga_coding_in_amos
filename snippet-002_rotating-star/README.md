## Rotating

A 2D rotating star at 50 FPS.
The scene is adapted from the demo "Happy New Year 2021" : https://www.pouet.net/prod.php?which=87666

![Rotating star](readImg/star.png)

### Inline 

Tables are quite slow in AMOS. In this example they are avoid by using simple variables (X0,XE0...) and no "for/next" loop.

### Integer arithmetic

There is no mathematical coprocessor on an standard Amiga 500. Numbers with commas go through a software calculation (# notation in AMOS). To obtain 50 FPS, it is necessary to avoid them and therefore all operations are done with integers.

