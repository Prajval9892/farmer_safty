# farmer_safty
#include<Servo.h>
Servo my_servo;
int ldr=A1;
float value;
int num=0;
void setup() {
  // put your setup code here, to run once:
  my_servo.attach(A0);
  pinMode(ldr,INPUT);
  Serial.begin(9600);
  

}

void loop() {
  // put your main code here, to run repeatedly:

 
     value=analogRead(ldr);
  Serial.println(value);
  my_servo.write(0);
  while(value>200)
  { value=analogRead(ldr);
  Serial.println(value);
    for(int i=0;i<=10;i++)
    {
      for(int j=0;j<=40;j++)
      {
        my_servo.write(j);
        delay(5);
      }
    }
  }

}
