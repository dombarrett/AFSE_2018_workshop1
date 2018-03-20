# Workshop 00
## Introduction to physical computing

Session: March 20th, 3:30pm

by NYU ITP students Daniella, Nate, Koji, and Dominic
& AFSE teacher Jonathan Rothman

(Taken from Aarón Montoya Moraga's notes from last year:
https://github.com/montoyamoraga/teaching_afse/blob/master/workshop_00.md
)

## What is physical computing?

Physical computing is an approach to learning how humans communicate through computers. It starts by considering how humans express themselves physically.

In physical computing, we do not take computer hardware (keyboard, screen, speakers, mouse) as a given. Instead, we take the human body as a given, and attempt to design within the limits of its expression.

We have to learn how a computer converts the changes in energy given off by our bodies, in the form of heat, light, sound, and so forth, into changing electronic signals that it can read and interpret.

We learn about the sensors that do this, and about very simple computers, called microcontrollers, that read sensors and convert their output into data. Finally, we learn how microcontrollers communicate with other computers.

Physical computing takes a hands-on approach, which means that you spend a lot of time building circuits, soldering, writing programs, building structures to hold sensors and controls, and figuring out how best to make all of these things relate to a person’s expression.

-- adapted from [Tom Igoe](http://www.tigoe.net/)'s [What is physical computing?](http://www.tigoe.net/blog/what-is-physical-computing/)

## Materials we will use

### Breadboard

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/breadboard.png "breadboard")

### Arduino Uno

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/arduino_uno.png "arduino uno")

### USB cable

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/usb_cable.png "usb cable")

### Jumper cables

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/jumper_cables.png "jumper cables")

### Resistors

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/resistors.png "resistors")

### LEDs

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/LEDs.png "LEDs")

### Potentiometer

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/potentiometer.png "Potentiometer")

### Pushbutton

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/pushbutton.png "Push button")

## What is an Arduino?

An Arduino is a microcontroller for building digital devices and interactive objets than can sense and control phyiscal devices.

You can donwload the software and read the manuals and reference at [arduino.cc](https://www.arduino.cc/).

## How does it work?

An Arduino has inputs and outputs that you can use as sensors and actuators.

## What for?

With sensors we can retrieve data from measurements from world that surrounds us, for example:
* Thermometer, measures temperature
* Photoresistor, measures amount of light
* Potentiometer. measures resistance

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/theremin.png "Theremin")

With actuators we can take data and transform it into different actions:
* Motors, move in different directions and speeds
* Solenoids, act as mechanical switches
* Robotic arm

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/robotic_arm.png "Robotic arm")

Arduino acts as an interface, that allows us to connect sensors, manipulate the data as we desire and then feed it to actuators to alter anything we want.

## Arduino programming

Arduino code is written using functions and variables.
* Variables allow us to store and manipulate data in the form of integer numbers, decimal numbers (float), text (String), etc.
* Functions are instructions that you can write so that Arduino performs actions such as reading data from inputs, writing data on the outputs, performing mathematical operations on variables, etc.

### setup() and loop()

The two main functions in Arduino are setup() and loop(). When Arduino is turned on, it executes setup() once and then executes loop() until it gets turned off.

Setup() is useful for setting up initial conditions and loop() is useful for performing repeated operations.

## Analog and digital

Arduino can read analog and digital signals. Analog data can have infinite values, such as decimal numbers. Digital data can take a finite number of values.

The exercise of wanting to measure temperature in a room is a good example for this. The temperature data is analog, the measurement has infinite decimals. Nonetheless, if we want to store it on a digital device, with limited memory, we have to approximate the number and store it as digital data.

## Good manners in programming

* Variables and functions should have meaningful names
* Print is your friend
* Comment everything you do
* Write code that is readable for your future self and other people

## Installation Instructions

Part 1: Create an account on Arduino Create and install the Arduino Plugin

Go to Arduino Create (https://create.arduino.cc/) and click “Sign in” at the top right of the page.

* Create a new account by clicking “Sign Up”.
* Use your AFSE email (up to the @ symbol) as your username. 
* Choose a password you will remember.
* Use your AFSE email as the email for your account.
* Click “Create account”.

Once you’ve created an account, go to your email inbox.  You should have a verify email at the top of your inbox.  Follow the instructions inside that email to verify your account.


Go back to https://create.arduino.cc/

* Click “Getting Started”.
* Click “Set up the Arduino Plugin to start coding online”.
* The plugin will download.
* Once fully downloaded, raise your hand and ask Mr. Rothman to install the plugin.

Nice work!  You should be able to use an Arduino with your Macbook!

## The Online Arduino IDE

The online Arduino IDE is where you program your Arduino, it looks like this:

![alt text](https://raw.githubusercontent.com/dombarrett/AFSE_2018_workshop1/master/arduinoOnlineIDE.png "Arduino IDE")

The software you write for your Arduino is called an sketch. Let's continue to our first Arduino sketch!

## Our first sketch: Blink

This sketch makes the built-in LED on the Arduino blink on an off.

```java
/*
  Blink
  Turns on an LED on for one second, then off for one second, repeatedly.

  Most Arduinos have an on-board LED you can control. On the UNO, MEGA and ZERO
  it is attached to digital pin 13, on MKR1000 on pin 6. LED_BUILTIN takes care
  of use the correct LED pin whatever is the board used.
  If you want to know what pin the on-board LED is connected to on your Arduino model, check
  the Technical Specs of your board  at https://www.arduino.cc/en/Main/Products

  This example code is in the public domain.

  modified 8 May 2014
  by Scott Fitzgerald

  modified 2 Sep 2016
  by Arturo Guadalupi

  modified by us for this workshop
*/

int pinLED = 13;

// the setup function runs once when you press reset or power the board
void setup() {
  // initialize digital pin LED_BUILTIN as an output.
  //syntax is:
  //pinMode(pinNumber, mode);
  pinMode(pinLED, OUTPUT);
}

// the loop function runs over and over again forever
void loop() {
  // turn the LED on (HIGH is the voltage level)
  digitalWrite(pinLED, HIGH);
  //wait for a second  
  delay(1000);
  // turn the LED off by making the voltage LOW
  digitalWrite(pinLED, LOW);
  //wait for a second
  delay(1000);                       
}
```

Exercise: modify this sketch, to make the LED blink faster or slower.

## Our Second sketch: push button

```java
/*
  Button

 Turns on and off a light emitting diode(LED) connected to digital
 pin 13, when pressing a pushbutton attached to pin 2.


 The circuit:
 * LED attached from pin 13 to ground
 * pushbutton attached to pin 2 from +5V
 * 10K resistor attached to pin 2 from ground

 * Note: on most Arduinos there is already an LED on the board
 attached to pin 13.


 created 2005
 by DojoDave <http://www.0j0.org>
 modified 30 Aug 2011
 by Tom Igoe

 This example code is in the public domain.

 http://www.arduino.cc/en/Tutorial/Button
 */

// constants won't change. They're used here to
// set pin numbers:
const int buttonPin = 2;     // the number of the pushbutton pin
const int ledPin =  13;      // the number of the LED pin

// variables will change:
int buttonState = 0;         // variable for reading the pushbutton status

void setup() {
  // initialize the LED pin as an output:
  pinMode(ledPin, OUTPUT);
  // initialize the pushbutton pin as an input:
  pinMode(buttonPin, INPUT);
}

void loop() {
  // read the state of the pushbutton value:
  buttonState = digitalRead(buttonPin);

  // check if the pushbutton is pressed.
  // if it is, the buttonState is HIGH:
  if (buttonState == HIGH) {
    // turn LED on:
    digitalWrite(ledPin, HIGH);
  } else {
    // turn LED off:
    digitalWrite(ledPin, LOW);
  }
}
```

Here is a diagram of the connection.

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/push_sketch.png "Fritzing pushbutton sketch")



## Extra time? Bonus third sketch: AnalogReadSerial

This sketch allows the Arduino to read from an analog input.

```java
/*
  AnalogReadSerial
  Reads an analog input on pin 0, prints the result to the serial monitor.
  Graphical representation is available using serial plotter (Tools > Serial Plotter menu)
  Attach the center pin of a potentiometer to pin A0, and the outside pins to +5V and ground.

  This example code is in the public domain.
*/

//the setup routine runs once when you press reset
void setup() {
  //initialize serial communication at 9600 bits per second
  Serial.begin(9600);
}

//the loop() functions executes over and over again forever
void loop() {
  //read the input on analog pin 0:
  int sensorValue = analogRead(A0);
  //print out to the console the value you read
  Serial.println(sensorValue);
  //delay in between reads for stability
  delay(1);       
}
```

Here is a diagram of the connection.

![alt text](https://github.com/aamontoya89/teaching_afse/raw/master/assets/analogReadSerial.png "Fritzing Analog read serial")

