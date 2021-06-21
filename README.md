# repository-of-the-terminal-report
## in order to get the terminal grade 

``` arduino
#include <Servo.h>
Servo topleftservo,toprightservo,Spinservo,launchservo;
int fortopl,fortopr,forlaunch;
int button = 7;
const int launchservo = 13; 
boolean lastButton = LOW; 
boolean tureButton = LOW; 
boolean launch = false;

void setup() {
	pinMode(launchservo,OUTPUT);
	pinMode(button,INPUT);
	pinMode(A0,INPUT);
	pinMode(6,OUTPUT);
	Spinservo.attach(6);
	topleftservo.attach(9);
	toprightservo.attach(10);
	buttservo.attach(11);
}

boolean deloop(boolean 1ast){
	boolean current = digitalRead(button); 
	if(last！= current){
		delay(10); 
		current = digitalRead(button); 
	}
	return current;
}

int base_degree = 0;
void loop() {
	int vrx = analogRead(A0);
	base_degree = map(vrx, 0, 1023, 0, 360);
	tureButton = deloop(1astButton); 
	Spinservo.write(base_degree);
	
	if(lastButton == LOW && tureButton == HIGH){
		launch =！launch;
	}
	lastButton = tureButton; 
	digitalWrite(launchservo,launch)
	
	if( launch == HIGH ){
		launchservo.write(90);
		delay(500);
		launchservo.write(120);
		delay(500);
		launchservo.write(90);
	}
	if( launch == LOW ){
		topleftservo.write(0);
		toprightservo.write(150);
		delay(800);
		topleftservo.write(150);
		toprightservo.write(0);
		delay(800);
		topleftservo.write(0);
		toprightservo.write(150);
	}
}
```
