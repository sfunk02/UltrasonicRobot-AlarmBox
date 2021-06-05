# AlarmBox

## Evidence
[Planning Document](https://docs.google.com/document/d/11-2wF_9yJS5I0nBnbIoVSM57Gn8QsEdFmUylcHFtpr0/edit)

[Onshape Document](https://cvilleschools.onshape.com/documents/62b61c312d311374f7377d1f/w/2b701c59b07ab7046ca70730/e/031eb83c64f35727659cf31c)

## Schedule

Week of 2-22: finish CAD

Week of 3-1: send in plans for laser cutting and 3d printing, finish writing the code

Week of 3-8: assemble/wire box, finalize coding, document project

#### Schedule Readjusted (3-11):

Week of 3-8: convert pseudo code to real code, make progress on CAD

Week of 3-15: finalize cad and code

Week of 3-22: cut, print, and assemble, test code

## Journal

### 2/22
* We accomplished doing a couple sides of the Onshape CAD
* We will probably need an extra week, seeing as we didn't finish the entire CAD this week, even though we were planning to.
* We were very busy the last week with other homework, but we are going to spend more time on engineering this week.

### 3/11
* We are currently behind schedule on CAD, but will try to catch up over the weekend. 
* This week, we are trying to turn the pseudo code into working code. 

### 3/16
* replaced fingerprint sensor with a button to streamline the design

## Pseudo-code

```C++
// alarm box that turns on when passed in front of
// Asher and Sam
// This code allows the alarm to make a beep when moved in front of, and turned off when 3 switches are correctly oriented, and a fingerprint scanner is held.


void setup() {
    // powerSwitch = 9
    
    // switchPin1 = 10
    // switchPin2 = 8
    // switchPin3 = 5
    
    // trigpin = 2
    // echopin = 3
}

void loop() {
  //powerswitchstate1 read (if this is off then nothing will work.)
  //trig and echo functions read
  // if number is less than [36(average size of door) - (width of box)]
    //sound on
  // if number remains at a constant high rate, 
    //sound off.
  
  // if sound on:
    //switchstate1 read
    //switchstate2 read
    //switchstate3 read
  
    // if all switches are on, it allows access to the scanner.
    // the scanner is necessary to turn off the sound
    // 1 or 2 of the switches will be backwards in comparison to the others, so you have to remember which way to flip all 3.
    // once the digital read picks up the correct configuration, and the fingerprint scanner is held, the sound goes off, and has a 1 minute cooldown before it can turn on again.
    
}


```

## Code

```C++
/*
Sam Funk & Asher Friedman
Alarm Box - makes a piezo buzzer beep when a HCSR-04 sensor detects a change in distance. It can only be turned off if the correct 2 out of 3 switches are turned on
and a button is pressed. 
*/

const int switchPin = 3  //These are the switches that must be correctly flipped to turn off the buzzer.
const int buzzer = 8    //Piezo buzzer pin
const int ultrasonicPin = 10  //HCSR-04 pin

#include <NewPing.h>  //NewPing library (for HCSR-04)

#define TRIGGER_PIN 12
#define ECHO_PIN 11
#define MAX_DISTANCE 200

NewPing myHC_SR04(TRIGGER_PIN, ECHO_PIN, MAX_DISTANCE);

int ledState = LOW;     // the current state of LED
int lastButtonState;    // the previous state of button
int currentButtonState; // the current state of button

void setup() {
  Serial.begin(9600);
  pinMode(switchPin, INPUT);
  pinMode(buzzer, OUTPUT);
  pinMode(ultrasonicPin, OUTPUT);
  currentButtonState = digitalRead(switch_Pin);
}

void loop() {
  int distance = myHC_SR04.ping_cm;
  Serial.println(myHC_SR04.ping_cm());
  delay(5);
  digitalWrite(ultrasonicPin, HIGH);
  delay(myHC_SR04.ping_cm()*10);
  digitalWrite(ultrasonicPin, LOW);
  delay(myHC_SR04.ping_cm()*10);

  lastButtonState    = currentButtonState;      // save the last state
  currentButtonState = digitalRead(BUTTON_PIN); // read new state

  
  
  
  if (digitalRead(switchPin) = HIGH) {
    noTone(buzzer); 
  
    if (distance < 90) {
    tone(buzzer, 1000);
    delay(500);
    noTone(buzzer);
    delay(500);
      if(lastButtonState == HIGH && currentButtonState == LOW) {
    Serial.println("The button is pressed");

    

    // control LED arccoding to the toggled state
    digitalWrite(buzzer, LOW); 
      }
  } 
  }
  
  else {
    noTone(buzzer);
  }
  
  }
  
  ```
