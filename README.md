# Assignment2
Control cp5


import controlP5.*;

float x; //declare x
float y; //declare y
float easing = 0.05;
float size;

Control cp5;
ColorPicker cp;

ControlP5 cp5Bar;
int colorMin =100;
int colorMax =100;

Range range;

ControlP5 cp5Checkbox;
CheckBox checkbox;

ControlP5 cp5Knob;
int ColorValue=50;

Knob myKnob;


//set up of background
void setup() {
  size(640, 360); 
  cursor(MOVE); //cursor CURSORICON  
}

void draw() { 
  background(#C3E3DD); //color code
  
  //four colors background
  if (mouseX < 320 && mouseY < 180)
  {
    fill (#D8C3E3);
    rect(0, 0, 320, 180); //topLeft
  }
  
  else if (mouseX > 320 && mouseY > 180)
  {
    fill (#FFC1C1);
    rect(320, 180, 320, 180);//BottomRight
  }
    
  else if (mouseX < 320 && mouseY > 180)
  {
    fill (#B3FFA2);
    rect(0,180,320,180);
  }
  
  else if (mouseX > 320 && mouseY < 180)
  {
    fill (#A2A6FF);
    rect (320,0,320,180);
  }
 
 
 //Ball
  float targetX = mouseX;
  float dx = targetX - x;
  x += dx * easing;
  
  float targetY = mouseY;
  float dy = targetY - y;
  y += dy * easing;
  noStroke();
 
  if (mouseX < 320 && mouseY < 180)
  {
    fill (#C762FF);
    ellipse(x, y, 66, 66); //topLeft
  }

  else if (mouseX > 320 && mouseY > 180)
  {
    fill (#FF4646);
    ellipse(x, y, 66, 66); 
  }
  
  else if (mouseX < 320 && mouseY > 180)
  {
    fill (#6FE352);
    ellipse (x,y,66,66);
  }
  
  else if (mouseX > 320 && mouseY < 180)
  {
    fill (#5B64FA);
    ellipse (x,y,66,66);
  }
  
  if (mousePressed == true)
  {
    fill(#FBFF89);
    ellipse(x, y, size,size); //yellow growing circle
    noStroke(); //no stroke for the circle
    size++;
    if(size>=66){
       size=30;
    }
  }
}
void keyPressed(){
   fill (random(255)); 
   ellipse(x,y,66,66);
   noStroke();
  }
