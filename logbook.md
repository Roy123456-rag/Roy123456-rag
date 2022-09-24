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



