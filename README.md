# IOT-LEVEL--1
> I'm Christeena Zacharia ,second year BCA(Bachelor of Computer Applications ) student at Kristu Jyoti College of Management and Technology. 
>
> 
>  The following are the IOT experiments I have done as part of the Kerala IOT challenge




|       | **EXPERIMENT**|
| ----------- | ----------- |
| 1     | HELLO WORLD LED BLINKING      |
| 2   | TRAFFIC LIGHT        |
| 3  | LED CHASING EFFECT    |
| 4   | BUTTON CONTROLLED  LED       |
| 5     |BUZZER      |
| 6   | RGB LED       |
| 7     | LDR LIGHT SENSOR     |
| 8  | FLAME SENSOR        |
| 9     | LM35 TEMPERATURE SENSOR   |
| 10   | IR REMOTE CONTROL USING TSOP|
| 11     |POTENTIOMETER ANALOG VALUE READING      |
| 12   |7 SEGMENT DISPLAY |




|       | **ASSIGNMENT**|
| ----------- | ----------- |
| 1     | AUTOMATIC NIGHT LAMP      |
| 2   | DIGITAL DICE USING LEDS   |




## EXPERIMENT 1 - HELLO WORLD LED BLINKING

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED
 - 220 ohm Resistor
 - breadboard
 - Jumper wires


![exp1](https://user-images.githubusercontent.com/81433705/144377740-6eb1cf8b-72b6-47c0-932a-e66309a90dcd.png)


### CODE
  
```
void setup()
{
  pinMode(8, OUTPUT);
}

void loop()
{
  digitalWrite(8, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(8, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
} 

```
 




## EXPERIMENT 2 - TRAFFIC LIGHT

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED-red,yellow,green
 - 220 ohm Resistor * 3
 - breadboard
 - Jumper wires

![exp2](https://user-images.githubusercontent.com/81433705/144702780-b26b5d78-4984-43f3-bf1e-d8ce7afb8b59.png)

### CODE

```
int redled =10; // initialize digital pin 10.
int yellowled =7; // initialize digital pin 7.
int greenled =4; // initialize digital pin 4.
void setup()
{
    pinMode(redled, OUTPUT);// set the pin with red LED as “output”
    pinMode(yellowled, OUTPUT); // set the pin with yellow LED as “output”
    pinMode(greenled, OUTPUT); // set the pin with green LED as “output”
}
void loop()
{
    digitalWrite(greenled, HIGH);//// turn on green LED
    delay(5000);// wait 5 seconds

    digitalWrite(greenled, LOW); // turn off green LED

    for(int i=0;i<3;i++)// blinks for 3 times
    {
         delay(500);// wait 0.5 second
         digitalWrite(yellowled, HIGH);// turn on yellow LED
         delay(500);// wait 0.5 second
         digitalWrite(yellowled, LOW);// turn off yellow LED
    } 
    delay(500);// wait 0.5 second
    digitalWrite(redled, HIGH);// turn on red LED
    delay(5000);// wait 5 seconds
    digitalWrite(redled, LOW);// turn off red LED
}

``` 










## EXPERIMENT 3 - LED CHASING EFFECT

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED * 6
 - 220 ohm Resistor * 6
 - breadboard
 - Jump wires

![exp1](https://user-images.githubusercontent.com/81433705/144703035-30f4660f-4869-4212-8e8e-8cd77b9aa536.png)

  
### CODE
```
int BASE = 2; // the I/O pin for the first LED
int NUM = 6; // number of LEDs
void setup()
{
   for (int i = BASE; i <BASE + NUM; i ++) 
   {
     pinMode(i, OUTPUT); // set I/O pins as output
   }
}
void loop()
{
   for (int i = BASE; i <=BASE + NUM; i ++) 
   {
     digitalWrite(i, LOW); // set I/O pins as “low”, turn off LEDs one by one.
     delay(100); // delay
   }
   for (int i = BASE; i <BASE + NUM; i ++) 
   {
     digitalWrite(i, HIGH); // set I/O pins as “high”, turn on LEDs one by one
     delay(100); // delay
   }  
}
``` 





## EXPERIMENT 4 - BUTTON CONTROOLED LED

### Components required

 - Arduino UNO Board
 - Button switch
 - USB Cable
 - Red m5 LED
 - 220 ohm Resistor
 - 10 K ohm Resistor
 - breadboard
 - Jump wires
  
![exp1](https://user-images.githubusercontent.com/81433705/144703262-b8aff3d4-d581-42e0-8fb4-fbff34c9fdbd.png)


### CODE

```
int ledpin=11;// initialize pin 11
int inpin=7;// initialize pin 7
int val;// define val
void setup()
{
    pinMode(ledpin,OUTPUT);// set LED pin as “output”
    pinMode(inpin,INPUT);// set button pin as “input”
}
void loop()
{
    val=digitalRead(inpin);// read the level value of pin 7 and assign if to val
    if(val==LOW)// check if the button is pressed, if yes, turn on the LED
    { 
        digitalWrite(ledpin,LOW);
    }
    else
    { 
        digitalWrite(ledpin,HIGH);}
    }
``` 







## EXPERIMENT 5 - BUZZER

### Components required

 - Arduino UNO Board
 - Buzzer
 - USB Cable
 - breadboard
 - Jump wires

### CODE
  
```
void setup() 
{ 
  pinMode(8, OUTPUT);
} 
void loop() 
{
  digitalWrite(8, HIGH);
  delay(1000);
  digitalWrite(8, LOW);
  delay(1000);
}
``` 
![exp1](https://user-images.githubusercontent.com/81433705/144703327-dcc8a1d4-0a7d-4078-be39-f5024aedfdcd.png)






## EXPERIMENT 6 - RGB LED
### Components required

 - Arduino UNO Board
 - USB Cable
 - RGB LED
 - 220 ohm Resistor * 3
 - breadboard
 - Jump wires


![exp1](https://user-images.githubusercontent.com/81433705/144703632-23bdb238-d54c-435d-acf3-31a18f5177ed.png)


### CODE
  
```
int red = 11;
int blue =10;
int green =9;
int val;
void setup() {
  pinMode(red, OUTPUT);
  pinMode(blue, OUTPUT);
  pinMode(green, OUTPUT);
  Serial.begin(9600);
}
void loop() 
{
for(val=255; val>0; val--)
  {
   analogWrite(11, val);
   analogWrite(10, 255-val);
   analogWrite(9, 128-val);
   delay(10); 
  }
for(val=0; val<255; val++)
  {
   analogWrite(11, val);
   analogWrite(10, 255-val);
   analogWrite(9, 128-val);
   delay(10); 
  }
 Serial.println(val, DEC);
}
``` 



## EXPERIMENT 7 - LDR LIGHT SENSOR

### Components required

 - Arduino UNO Board
 - USB Cable
 - Photo Resistor
 - Red LED
 - 220 ohm Resistor
 - 10 K ohm Resistor
 - breadboard
 - Jump wires


![exp1](https://user-images.githubusercontent.com/81433705/144706212-c1f734ef-c952-4aae-bdc8-5e9f60da302d.png)


### CODE
  
```
int potpin=0;
int ledpin=11;
int val=0;
void setup()
{
pinMode(ledpin,OUTPUT);
Serial.begin(9600);
}
void loop()
{
val=analogRead(potpin);
Serial.println(val);
analogWrite(ledpin,val/4);
delay(10);
}

```
 
 
 
 
 
 
 
## EXPERIMENT 8 - FLAME SENSOR

### Components required

 - Arduino UNO Board
 - USB Cable
 - Flame Sensor
 - Buzzer

 - 10 k ohm Resistor
 - breadboard
 - Jump wires


![exp1](https://user-images.githubusercontent.com/81433705/144708600-f43f6cd2-4809-455f-aa55-799f8e5c8e73.jpg)


### CODE
  
```
void setup()
{
  pinMode(8, OUTPUT);
}

void loop()
{
  digitalWrite(8, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(8, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
} 

```
 
 
 
 
 
 
 
 
 
 
## EXPERIMENT 9-LM35 TEMPERATURE SENSOR

### Components required

 - Arduino UNO Board
 - LM35 
 - USB Cable
 
 - breadboard
 - Jump wires


![exp1](https://user-images.githubusercontent.com/81433705/144706594-16044dc9-3243-4508-850e-c16c61a6c9ac.png)


### CODE
  
```
void setup()
{
  pinMode(LED_BUILTIN, OUTPUT);
}

void loop()
{
  digitalWrite(LED_BUILTIN, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(LED_BUILTIN, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
}
```
 
 
 
 
 
 
 
 
 
 
 
## EXPERIMENT 10 - HELLO WORLD LED BLINKING

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED
 - 220 ohm Resistor
 - breadboard
 - Jump wires


![exp1](https://user-images.githubusercontent.com/81433705/144377740-6eb1cf8b-72b6-47c0-932a-e66309a90dcd.png)


### CODE
  
```
void setup()
{
  pinMode(8, OUTPUT);
}

void loop()
{
  digitalWrite(8, HIGH);
  delay(1000); // Wait for 1000 millisecond(s)
  digitalWrite(8, LOW);
  delay(1000); // Wait for 1000 millisecond(s)
} 

```
 
 
 
 
 
 
 
## EXPERIMENT 11 - POTENTIOMETER ANALOG VALUE READING

### Components required

 - Arduino UNO Board
 - USB Cable

 - 10K Potentiometer
 - breadboard
 - Jump wires


![exp1](https://user-images.githubusercontent.com/81433705/144706795-5606ecec-6d25-4adf-96e8-0e54b2ab5a97.png)


### CODE
  
```
int potpin=0;
int ledpin=13;
int val=0;//
void setup()
{
pinMode(ledpin,OUTPUT);
Serial.begin(9600);
}
void loop()
{
digitalWrite(ledpin,HIGH);
delay(50);
digitalWrite(ledpin,LOW);
delay(50);
val=analogRead(potpin);
Serial.println(val);
}

```
 
 
 
 
 
## EXPERIMENT 12- 7 SEGMENT DISPLAY
### Components required

 - Arduino UNO Board
 - USB Cable
 - 1 Digit LED Segment Display
 - 220 ohm Resistor * 8
 - breadboard
 - Jumper wires


![exp1](https://user-images.githubusercontent.com/81433705/144707481-6e802623-bebf-4273-b305-04fc2eca58bd.png)


### CODE
  
```
int a=7;
int b=6;
int c=5;
int d=10;
int e=11;
int f=8;
int g=9;
int dp=4;
void digital_0(void) 
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,LOW);
digitalWrite(dp,LOW);
}
void digital_1(void) 
{
unsigned char j;
digitalWrite(c,HIGH);
digitalWrite(b,HIGH);
for(j=7;j<=11;j++)
digitalWrite(j,LOW);
digitalWrite(dp,LOW);
}
void digital_2(void) 
{
unsigned char j;
digitalWrite(b,HIGH);
digitalWrite(a,HIGH);
for(j=9;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
digitalWrite(c,LOW);
digitalWrite(f,LOW);
}
void digital_3(void) 
{digitalWrite(g,HIGH);
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(dp,LOW);
digitalWrite(f,LOW);
digitalWrite(e,LOW);
}
void digital_4(void) 
{digitalWrite(c,HIGH);
digitalWrite(b,HIGH);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
digitalWrite(a,LOW);
digitalWrite(e,LOW);
digitalWrite(d,LOW);
}
void digital_5(void) 
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b, LOW);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void digital_6(void) 
{
unsigned char j;
for(j=7;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(c,HIGH);
digitalWrite(dp,LOW);
digitalWrite(b,LOW);
}
void digital_7(void) 
{
unsigned char j;
for(j=5;j<=7;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
for(j=8;j<=11;j++)
digitalWrite(j,LOW);
}
void digital_8(void) 
{
unsigned char j;
for(j=5;j<=11;j++)
digitalWrite(j,HIGH);
digitalWrite(dp,LOW);
}
void digital_9(void) 
{
unsigned char j;
digitalWrite(a,HIGH);
digitalWrite(b,HIGH);
digitalWrite(c,HIGH);
digitalWrite(d,HIGH);
digitalWrite(e, LOW);
digitalWrite(f,HIGH);
digitalWrite(g,HIGH);
digitalWrite(dp,LOW);
}
void setup()
{
int i;
for(i=4;i<=11;i++)
pinMode(i,OUTPUT);
}
void loop()
{
while(1)
{
digital_0();
delay(1000);
digital_1();
delay(1000);
digital_2();
delay(1000); 
digital_3();
delay(1000);
digital_4();
delay(1000); 
digital_5();
delay(1000); 
digital_6();
delay(1000);
digital_7();
delay(1000); 
digital_8();
delay(1000); 
digital_9();
delay(1000); 
}}
```
 
 
 
 
 
 
 
 
 
 
 
## ASSIGNMENT 1 -AUTOMATIC NIGHT LAMP MODEL USING LDR AND LED
 
### CODE
  
```
void setup()
  {
   Serial.begin(9600);
   pinMode(10,OUTPUT);
  pinMode(A0, INPUT); 
  }

void loop()
  {
    int c=analogRead(A0);  
 
      
    if(c<500)
      {
        digitalWrite(10,LOW);
      }
    
    else
      {
        digitalWrite(10,HIGH);
      }
}




```
 
 
 ![assign 1](https://user-images.githubusercontent.com/81433705/144708041-df995fe4-a9fd-4493-abe3-ffd7c149c260.png)

 
## ASSIGNMENT 2 - DIGITAL DICE USING 6 LEDS AND 1 PUSH BUTTON
### CODE
  
```
#define DEBUG 0


int first = 2;
int second = 3;
int third = 4;
int fourth = 5;
int fifth = 6;
int sixth = 7;


int button = 12;

int pressed = 0;

void setup() {
 
  for (int i=first; i<=sixth; i++) {
    pinMode(i, OUTPUT);
  }
 
  pinMode(button, INPUT);
  

  randomSeed(analogRead(0));

 
  #ifdef DEBUG
    Serial.begin(9600);
  #endif

}

void buildUpTension() {
  
  for (int i=first; i<=sixth; i++) {
    if (i!=first) {
      digitalWrite(i-1, LOW);
    }
    digitalWrite(i, HIGH);
    delay(100);
  }
  
  for (int i=sixth; i>=first; i--) {
    if (i!=sixth) {
      digitalWrite(i+1, LOW);
    }
    digitalWrite(i, HIGH);
    delay(100);
  }
}

void showNumber(int number) {
  digitalWrite(first, HIGH);
  if (number >= 2) {
    digitalWrite(second, HIGH);
  }
  if (number >= 3) {
    digitalWrite(third, HIGH);    
  }
  if (number >= 4) {
    digitalWrite(fourth, HIGH);    
  }
  if (number >= 5) {
    digitalWrite(fifth, HIGH);    
  }
  if (number == 6) {
    digitalWrite(sixth, HIGH);    
  }
}

int throwDice() {
  
  int randNumber = random(1,7);
  
  #ifdef DEBUG
    Serial.println(randNumber);
  #endif
  
  return randNumber;
}

void setAllLEDs(int value) {
  for (int i=first; i<=sixth; i++) {
    digitalWrite(i, value);
  }
}

void loop() {
  
  pressed = digitalRead(button);

  if (pressed == HIGH) {
  
    setAllLEDs(LOW);
    
    buildUpTension();
    int thrownNumber = throwDice();
    showNumber(thrownNumber);
  } 

}


```
 
 
 ![assign 1](https://user-images.githubusercontent.com/81433705/144708298-d26736a7-04c7-4936-ad6a-8eda53e5b93a.png)

 
 
 
 


