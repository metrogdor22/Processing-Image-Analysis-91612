Processing-Image-Analysis-91612
===============================
PImage img;
ArrayList xList;
ArrayList yList;
//This threshold determines what is considered a "black" pixel.
//I made it 20 so that it also includes dark gray.
int threshold = 20;

void setup() {
  size(100,100);
  img = loadImage("image.jpg");
  image(img,0,0);
}

void draw() {
  //Here it scans through each pixel of the image.
  for (int ix = 0; ix < img.width; ix++) {
    for (int iy = 0; iy < img.height; iy++) {
      //If the brightness of the pixel at (ix,iy) is less than
      //the threshold
      if (brightness(get(ix,iy)) < threshold) {
        //Add ix, and iy to their respective ArrayList.
        //This is where I'm having a problem. It's returning a
        //NullPointerException on "xList.add(ix)"
        xList.add(ix);
        yList.add(iy);
        //Print out eack black coordinate
        println("X:" + ix + " Y:" + iy);
      }
    }
  }
}