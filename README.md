# Experiment-no-7-DC-Motor-Speed-Control-Using-Arduino
### AIM : To control the speed and the direction of a DC motor using L293D driver ic( H- bridge)

### Components Required:
•	Arduino UNO board
•	L293D driver
•	12V DC motor
•	10K ohm potentiometer
•	Pushbutton
•	12V source
•	Breadboard
•	Jumper wires
### THEORY 
The L293D quadruple half-H drivers chip allows us to drive 2 motors in both directions, with two PWM outputs from the Arduino we can easily control the speed as well as the direction of rotation of one DC motor. (PWM: Pulse Width Modulation).
Arduino DC motor control circuit:
Project circuit schematic diagram is the one below.

![image](https://user-images.githubusercontent.com/36288975/167763051-b230c183-afc5-46f2-ba95-0f95e10dd6c9.png)
FIGURE-01 H BRIDGE CIRUCIT INTERFACE 
 
The speed of the DC motor (both directions) is controlled with the 10k potentiometer which is connected to analog channel 0 (A0) and the direction of rotation is controlled with the push button which is connected to pin 8 of the Arduino UNO board. If the button is pressed the motor will change its direction directly.
The L293D driver has 2 VCCs: VCC1 is +5V and VCC2 is +12V (same as motor nominal voltage). Pins IN1 and IN2 are the control pins where:
![image](https://user-images.githubusercontent.com/36288975/167763120-1421c2c5-8381-49eb-b376-03f6e1113b7a.png)
TABLE-01 EXITATION TABLE FOR H BRIDGE 

As shown in the circuit diagram we need only 3 Arduino terminal pins, pin 8 is for the push button which toggles the motor direction of rotation. Pins 9 and 10 are PWM signal outputs, at any time there is only 1 active PWM, this allows us to control the direction as well as the speed by varying the duty cycle of the PWM signal. The active PWM pin decides the motor direction of rotation (one at a time, the other output is logic 0).

PROGRAM FOR STIMULATION:
```
Name: Balaji J
Roll  no: 212221243001

const int motorpin1 = 5;
const int motorpin2 = 6;


void setup()
{
  pinMode(motorpin1,OUTPUT);
  pinMode(motorpin2,OUTPUT);
}

void loop()
{
  
  digitalWrite(motorpin1,HIGH);
  delay(2000);
  digitalWrite(motorpin2,LOW);
  delay(200);
  
 
```
PROGRAM FOR RPM:
```
#define motorIn1 5
#define motorIn2 6

void setup()
{
  pinMode(motorIn1,OUTPUT);
  pinMode(motorIn2,OUTPUT);
}
void loop()
{
  clockwise(250);
  delay(6000);
  counterclockwise(64);
  delay(6000);
}
void counterclockwise(int speed)
{
  analogWrite(motorIn1,speed);
  analogWrite(motorIn2,0);
}

void clockwise(int speed)
{
  
  analogWrite(motorIn1,0);
  analogWrite(motorIn2,speed);
}


```

### OUTPUT

![image](https://user-images.githubusercontent.com/114234865/203043569-66c3de77-d3c4-475d-9eba-baf6e6934daa.png)


### GRAPH AND TABULATION 

![image](https://user-images.githubusercontent.com/114234865/203043647-4c3e1b12-95b3-4edc-90a9-65121825243b.png)

![image](https://user-images.githubusercontent.com/114234865/203047284-52bad2b0-1faf-4878-ac54-f5b73785c537.png)

![image](https://user-images.githubusercontent.com/114234865/203047386-35d509a4-f1d3-4e34-9223-e8ca783acb2f.png)

![image](https://user-images.githubusercontent.com/114234865/203047430-024dd93d-36ec-41aa-9196-0bed01c568ab.png)

### RESULTS
Thus, the speed and the direction of a DC motor using L293D driver ic( H- bridge) is controlled.
