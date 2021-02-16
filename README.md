# AlarmBox

## Evidence
[Planning Document](https://docs.google.com/document/d/11-2wF_9yJS5I0nBnbIoVSM57Gn8QsEdFmUylcHFtpr0/edit)

[Onshape Document](https://cvilleschools.onshape.com/documents/62b61c312d311374f7377d1f/w/2b701c59b07ab7046ca70730/e/031eb83c64f35727659cf31c)
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
