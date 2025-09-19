# Proyecto-inform-tico-1-4-4ta

#include <Servo.h>

#include <Servo.h>
#define atras 2
#define adelante 3

Servo servo1,servo2;
int grados;
bool avanzar,retroceder;
void setup()
{
	servon1.attach(A1);
  	servon2.attach(A2);
  	servon1.write(0);
  	servon2.write(0);
	pinMode(adelante, INPUT);
  	pinMode(atras, INPUT);
    Serial.begin(9600);
}

void loop()
{
  
  avanzar=digitalRead(3);
  retroceder=digitalRead(2);
  if (avanzar==LOW){
  	avanza();
  }
  if (retroceder==LOW){
    atras();
  }
  Serial.println(avanzar);
  Serial.println(retroceder);

}
void avanza(){
  	grados+=10;
	servon1.write(grados);
  	servon2.write(grados);
     delay(1000);
  
}
void atras(){
  	grados-=10;
	servon1.write(grados);
  	servon2.write(grados);
     delay(1000);
  
}
