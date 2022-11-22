![Birmingham City University Logo!](/assets/bculogo.png "BCU Logo")


# Logbook - Computer Systems  
  
### Name: Richard Davies  
### BCU ID: S13188948
### WTU ID:   
  
## Week 1 - Introduction and Setup  
*This is where you can write a brief description explaining what you have done in the class today, you should keep this brief and ensure that it is concice.*
This week was spent learning about computer systems, conducting a big overview theory session to give us a deeper understanding of computers and related electronics.

### Evidence 
*Here you can include pictures of what you have done, you must also include any code that you have done, especially if you have been working on Arduinos or Raspberry Pis*

```c 
int code = 1; //If there is code this week, you must include evidence of it. 

if (code == 1){ 
    print("You will get marks for it");
}
else{
    print("You will not get marks for it if you don't include it");
}
```
### Weekly Conclusion 
*Discuss the skills and techniques that you have learnt throughout the week, and what benefit they will have to your assessment and future work.*
We have learnt about electronic systems and the open lectures have made us even more eager for future courses.

## Week 2 - Don't Get Zapped
This lesson introduced us to many of the physical electronic elements and the associated roles that they play in circuits.
## Week 3 - What is Arduino?
In this lesson, we have learned Arduino, which is a convenient and flexible open source electronic prototype platform. Contains hardware (various models of Arduino boards) and software (Arduino IDE). Developed by a European development team in the winter of 2005. Its members include Massimo Banzi, David Cuartielles, Tom Igoe, Gianluca Martino, David Mellis and Nicholas Zambetti. [1]
It is built on the open source simple I/O interface Edition and has a Processing/Wiring development environment using languages like Java and C. It mainly consists of two parts: the hardware part is an Arduino circuit board that can be used for circuit connection; The other is the Arduino IDE, the program development environment on your computer.
Arduino uses various sensors to sense the environment and controls lights, motors, and other devices to feedback and influence the environment. The microcontroller on the board can be programmed by the Arduino programming language, compiled into binary files, and burned into the microcontroller. An Arduino-based project can include Arduino and other software running on a PC that communicates with each other (Flash, Processing, MaxMSP, for example).

## Week 4 - Arduino but Better.
```c
int ledPin1 = 13;
int ledPin2 = 12;
int ledPin3 = 11;

int buttonPin = 2;

int buttonState = 0;

int timeDelay = 100;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  
  pinMode(ledPin1,OUTPUT);
  pinMode(ledPin2,OUTPUT);
  pinMode(ledPin3,OUTPUT);
  pinMode(buttonPin,INPUT);

}

void loop() {
  // put your main code here, to run repeatedly:

  buttonState = digitalRead(buttonPin);
  if(buttonState == HIGH){
    digitalWrite(ledPin1,HIGH);
    digitalWrite(ledPin2,LOW);
    digitalWrite(ledPin3,HIGH);
  }else
  {
    digitalWrite(ledPin1,LOW);
    digitalWrite(ledPin2,HIGH);
    digitalWrite(ledPin3,LOW);
  }

}
```

## Week 5 - Expanded Universe
In this lesson we have learnt to control the light and dark changes of a small light bulb by means of a switch, using a circuit connected to a resistor plugged in, connected to a computer for power supply and then fitted with our switch to achieve the light and dark of the small light bulb.

In this lesson, we learned how to use a switch on the breadboard to control the light of the small light bulb. Of course, this is different from the former, the three light bulbs are constantly flashing, which is controlled by our code.
```c
#define trigPin 3
#define echoPin 2
long duration;
int distance;
int led1 = 9;
int led2 = 10;
int led3 = 11;
int led4 = 12;
int led5 = 13;
void setup() {
  // put your setup code here, to run once:
 pinMode(trigPin,OUTPUT);
 pinMode(echoPin,INPUT);
 Serial.begin(9600);
 pinMode(led1,OUTPUT);
  pinMode(led2,OUTPUT);
   pinMode(led3,OUTPUT);
    pinMode(led4,OUTPUT);
     pinMode(led5,OUTPUT);
 
}

void loop() {
  // put your main code here, to run repeatedly:
  digitalWrite(trigPin,HIGH);
  delayMicroseconds(2);
  digitalWrite(trigPin,HIGH);
  delayMicroseconds(10);
  digitalWrite(trigPin,HIGH);

  duration = pulseIn(echoPin,HIGH);
  distance = duration * 0.034 / 2;
  Serial.print("Distance: ");
  Serial.print(distance);
  Serial.print("cm");
  if( distance<5 ){
    digitalWrite(led1,HIGH);
    digitalWrite(led2,HIGH);
    digitalWrite(led3,HIGH);
    digitalWrite(led4,HIGH);
    digitalWrite(led5,HIGH);
  }
  delay(100);
}
```

## Week 7 - Compute It
This week we have been learning about the use of code to display values on a digital screen, using a circuit plug-in that allows us to display code on the computer that produces whatever we type.

Made LED display screen, can show our code into the display.
```c
int sensorValue;
float voltage;
float resistance;
int ledPin1 = 9;
int ledPin2 = 10;
int ledPin3 = 11;
int ledPin4 = 12;
int ledPin5 = 13;

void setup() {
  // put your setup code here, to run once:
  Serial.begin(9600);
  pinMode(ledPin1,OUTPUT);
  pinMode(ledPin2,OUTPUT);
  pinMode(ledPin3,OUTPUT);
  pinMode(ledPin4,OUTPUT);
  pinMode(ledPin5,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:

  sensorValue = analogRead(A0);
  //Serial.println(sensorValue);
  voltage = sensorValue * (5.0/ 1023.0);
  resistance = map(sensorValue,0,1023,10000,0);

  Serial.print("Voltage: ");
  Serial.print(voltage);
  Serial.println("v");
  Serial.print("Resistance:");
  Serial.print(resistance);
  Serial.println("ohms");
  delay(1);
  if (voltage >= 1.00)
  {
    digitalWrite(ledPin1,HIGH);
  }
  if (voltage >= 2.00)
  {
    digitalWrite(ledPin2,HIGH);
  }
  if (voltage >= 3.00)
  {
    digitalWrite(ledPin3,HIGH);
  }
  if (voltage >= 4.00)
  {
    digitalWrite(ledPin4,HIGH);
}
if (voltage >= 5.00)
  {
    digitalWrite(ledPin5,HIGH);
  }
}
```
### Weekly Conclusion
We learned the display operation, input different letters or numbers in the computer, can be displayed in it.

## week8-Printed Circuit Boards
This week in class we have learnt how to control the blinking of LED bulbs and how often they blink, how to put together wiring in an Arduino breadboard, the basics of binary and the ability to extrapolate binary.  which then corresponds bit by bit to perform the operation.
```c
int one = 9;
int two = 10;
int four = 11;

void setup() {
  // put your setup code here, to run once:
pinMode(one,OUTPUT);
pinMode(two,OUTPUT);
pinMode(four,OUTPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
multiPlex(0,0,0,500);
multiPlex(0,1,1,250);
multiPlex(1,1,1,100);
}
void multiPlex(bool a,bool b,bool c,int del){
  digitalWrite(one,c);
  digitalWrite(two,b);
  digitalWrite(four,a);
  delay(del);
}
```
### Weekly Conclusion
The lesson concludes that the blinking of each small LED bulb is firmly tied to the binary. They are so closely related that each one of them will not respond if something goes wrong with the little bulb. This lesson has taught and taught you the rules about small light bulbs and binary.


## Week 9
The class has learned the installation of membrane buttons on an Arduino breadboard and has been able to use the code flexibly to implement membrane buttons that respond on the serial monitor. It is also possible to connect LED electronic displays for interconnection.
### Evidence 
```c
// This file contains predefined setup for various Adafruit Matrix Keypads.
#ifndef __KEYPAD_CONFIG_H__
#define __KEYPAD_CONFIG_H__

#if defined(KEYPAD_PID3844)
const byte ROWS = 4; // rows
const byte COLS = 4; // columns
// define the symbols on the buttons of the keypads
char keys[ROWS][COLS] = {{'1', '2', '3', 'A'},
                         {'4', '5', '6', 'B'},
                         {'7', '8', '9', 'C'},
                         {'*', '0', '#', 'D'}};
byte rowPins[ROWS] = {R1, R2, R3,
                      R4}; // connect to the row pinouts of the keypad
byte colPins[COLS] = {C1, C2, C3,
                      C4}; // connect to the column pinouts of the keypad
#endif

#if defined(KEYPAD_PID1824) || defined(KEYPAD_PID3845) || defined(KEYPAD_PID419)
const byte ROWS = 4; // rows
const byte COLS = 3; // columns
// define the symbols on the buttons of the keypads
char keys[ROWS][COLS] = {
    {'1', '2', '3'}, {'4', '5', '6'}, {'7', '8', '9'}, {'*', '0', '#'}};
byte rowPins[ROWS] = {R1, R2, R3,
                      R4};         // connect to the row pinouts of the keypad
byte colPins[COLS] = {C1, C2, C3}; // connect to the column pinouts of the
                                   // keypad
#endif

#if defined(KEYPAD_PID1332)
const byte ROWS = 1; // rows
const byte COLS = 4; // columns
// define the symbols on the buttons of the keypads
char keys[ROWS][COLS] = {
    {'1', '2', '3', '4'},
};
byte rowPins[ROWS] = {R1}; // connect to the row pinouts of the keypad
byte colPins[COLS] = {C1, C2, C3,
                      C4}; // connect to the column pinouts of the keypad
#endif
#endif
```
### Weekly Conclusion
We learned to use the touch pad to display the operation, which will help us a lot later.


## week10 
In this lesson we learned what is PCB, the Chinese name for printed circuit board, also known as printed circuit board, is an important electronic component, is the support body of electronic components, is the carrier of the electrical connection of electronic components because it is made using electronic printing technology, it is called "printed" circuit board.The pcb allows us to view the various circuit design concepts and styles in the port and to get an easier understanding of the components and secrets.
```c
#include <SPI.h>
#include <Wire.h>
#include <Adafruit_GFX.h>
#include <Adafruit_SSD1306.h>

#define SCREEN_WIDTH 128 // OLED display width, in pixels
#define SCREEN_HEIGHT 64 // OLED display height, in pixels

#define OLED_RESET -1


#define SCREEN_ADDRESS 0x3C ///< See datasheet for Address; 0x3D for 128x64, 0x3C for 128x32
Adafruit_SSD1306 display(SCREEN_WIDTH, SCREEN_HEIGHT, &Wire, OLED_RESET);

void setup() {
  // put your setup code here, to run once:
  display.begin(SSD1306_SWITCHCAPVCC,SCREEN_ADDRESS);
}

void loop() {
  // put your main code here, to run repeatedly:

  display.clearDisplay();
  display.setTextSize(2);
  display.setTextColor(WHITE);
  display.setCursor(0,0);
  display.print("");
  display.display();
  delay(1000);

}
```


### Weekly Conclusion
We learned the circuit diagram of PCB, which can bring us a greater role in the future.


## week11
## Week 11 - Introduction and Setup  
This week was spent learning about stepper motor installation on an Arduino breadboard and implementing code to control the stepper motor. We have gained an in-depth understanding and knowledge of what stepper motors do and how they work.
### Evidence 
```c
#include<Stepper.h>

const int StepsPerRevolution = 2038;

Stepper myStepper = Stepper(StepsPerRevolution,8,10,9,11);
int buttonPin = 6;
int motSpeed;
void setup() {
  // put your setup code here, to run once:
  
pinMode(buttonPin,INPUT);
}

void loop() {
  // put your main code here, to run repeatedly:
  motSpeed = map(analogRead(A0),0,1023,1,15);
  Serial.println(motSpeed);
  if(digitalRead(buttonPin) == HIGH){
myStepper.setSpeed(motSpeed);
myStepper.step(StepsPerRevolution);
delay(1000);
myStepper.step(StepsPerRevolution);
delay(1000);
}
}
```
### Weekly Conclusion 
This week we have learnt and mastered about the installation and practical application of stepper motors, gaining an in-depth understanding of the code that can control stepper motors in conjunction with arduino.






