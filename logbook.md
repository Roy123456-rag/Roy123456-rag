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
## Week 5 - Expanded Universe
In this lesson, we learned how to use a switch on the breadboard to control the light of the small light bulb. Of course, this is different from the former, the three light bulbs are constantly flashing, which is controlled by our code.

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
## Week 7 - Compute It
Made LED display screen, can show our code into the display.

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

## week8
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

## week9
int one = 11;
int two = 10;
int four = 9;

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

## week10
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






