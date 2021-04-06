# Arduino-ButtonAndBlink
IGME470 - From the Arduino Editor
Project: Musical Light Show
Post: https://mililani-physicalcomp.blogspot.com/2021/03/project-1-blink-mini-light-show.html

# Code:
```/*
  Button

  Turns on and off a light emitting diode(LED) connected to digital pin 13,
  when pressing a pushbutton attached to pin 2.

  The circuit:
  - LED attached from pin 13 to ground
  - pushbutton attached to pin 2 from +5V
  - 10K resistor attached to pin 2 from ground

  - Note: on most Arduinos there is already an LED on the board
    attached to pin 13.

  created 2005
  by DojoDave <http://www.0j0.org>
  modified 30 Aug 2011
  by Tom Igoe

  This example code is in the public domain.

  http://www.arduino.cc/en/Tutorial/Button
*/

// constants won't change. They're used here to set pin numbers:
const int buttonPin = 2;     // the number of the pushbutton pin
const int buttonSwitch2 = 9;

const int greenLED =  5; // green
const int blueLED = 6; //blue
const int whiteLED = 5; //white
const int redLED = 7; //red

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status
int buttonState2= 0;

void setup() {
  // initialize the LED pin as an output:
  pinMode(greenLED, OUTPUT);
  pinMode(blueLED, OUTPUT);
  pinMode(whiteLED, OUTPUT);
  pinMode(redLED, OUTPUT);
  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT);
  pinMode(buttonSwitch2, INPUT);
}

void loop() {
  // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);
  buttonState2 = digitalRead(buttonSwitch2);

  // check if the pushbutton is pressed. If it is, the buttonState is HIGH:
  if (buttonState == HIGH) {
    // turn LED on:
    digitalWrite(greenLED, HIGH);
    digitalWrite(whiteLED, HIGH);
    
  } else {
    // turn LED off:
    digitalWrite(greenLED, LOW);
    digitalWrite(whiteLED, LOW);
  }
  
  //blue LED to blink on high
  if(buttonState2 == HIGH)
  {
    digitalWrite(blueLED, HIGH);
    delay(250);
    digitalWrite(blueLED, LOW);
    delay(250);
  }
  if(buttonState2 == LOW)
  {
    digitalWrite(blueLED, LOW);
  }
  
  //always make red LED blink
  digitalWrite(redLED, HIGH);
  delay(2000);
  digitalWrite(redLED, LOW);
  delay(1000);
  
}
```
