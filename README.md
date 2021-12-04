# IOT-LEVEL--1


## EXPERIMENT 1 - HELLO WORLD LED BLINKING

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
 




## EXPERIMENT 2 - TRAFFIC LIGHT

### Components required

 - Arduino UNO Board
 - USB Cable
 - LED-red,yellow,green
 - 220 ohm Resistor * 3
 - breadboard
 - Jump wires

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
![exp1](https://user-images.githubusercontent.com/81433705/144703035-30f4660f-4869-4212-8e8e-8cd77b9aa536.png)




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
![exp1](https://user-images.githubusercontent.com/81433705/144703262-b8aff3d4-d581-42e0-8fb4-fbff34c9fdbd.png)






## EXPERIMENT 5 - BUZZER

### Components required

 - Arduino UNO Board
 - Buzzer
 - USB Cable
 - breadboard
 - Jump wires
  
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
![exp1](https://user-images.githubusercontent.com/81433705/144703632-23bdb238-d54c-435d-acf3-31a18f5177ed.png)



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


![exp1](https://user-images.githubusercontent.com/81433705/144377740-6eb1cf8b-72b6-47c0-932a-e66309a90dcd.png)


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
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 
 


