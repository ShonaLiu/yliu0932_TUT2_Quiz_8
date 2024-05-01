# yliu0932_TUT2_Quiz_8

# Part 1: Imaging Technique Inspiration

It is using the random function to create lines in a drawing. This inspired me to use it in creating the San Giorgio Maggiore at Dusk since the sky of the drawing is not clear. It is in red, orange, yellow, green, and blue color. I can utilize this imaging technique to create the sky as well as some of the water's surface. Since Monet created the drawing when he started to lose eye sights, this type of imaging technique helps illustrate a feeling of seeing not clearly which perfectly represents the background story of Monet when he created this drawing.

![test](https://happycoding.io/tutorials/p5js/images/random-15.png)
![test](https://happycoding.io/tutorials/p5js/images/random-18.png)


# Part 2: Coding Technique Exploration
The coding technique I found is using the random function. It will create a random moving line that can also change its color. By limiting the area that the line can go, I can create the effect in certain areas. Using the sky of the drawing as an example, I can use this coding technique to recreate the different colors of the sky by limiting where the line can go.  

```
var x;
var y;
var r;
var g;
var b;

function setup() {
  createCanvas(200, 200);
  
  x = width / 2;
  y = width / 2;
  
  r = random(0, 255);
  g = random(0, 255);
  b = random(0, 255);
  
  background(32);
}

function draw() {

  // randomly move line
  var randomValue = random();
  if(randomValue < .25){
    x--;
  }
  else if(randomValue < .5){
    x++;
  }
  else if(randomValue < .75){
    y--;
  }
  else{
    y++;
  }
  
  // wrap around left and right sides
  if(x < 0){
    x = width;
  }
  else if(x > width){
    x = 0;
  }
  
  // wrap around top and bottom sides
  if(y < 0){
    y = height;
  }
  else if(y > height){
    y = 0;
  }
  
  // randomly change color
  r += random(-1, 1);
  g += random(-1, 1);
  b += random(-1, 1);
  
  // don't let values go outside 0-255 range
  r = constrain(r, 0, 255);
  g = constrain(g, 0, 255);
  b = constrain(b, 0, 255);
  
  stroke(r, g, b);
  
  point(x, y);
}
```
