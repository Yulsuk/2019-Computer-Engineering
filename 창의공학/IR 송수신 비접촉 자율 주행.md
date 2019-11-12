1. 아두이노 코드

#include <Servo.h>
 
Servo servoLeft;
Servo servoRight;
 
void setup()                           
{
  pinMode(10, INPUT);  pinMode(9, OUTPUT); 
  pinMode(3, INPUT);  pinMode(2, OUTPUT);
  
  servoLeft.attach(13);                
  servoRight.attach(12);           
}  
 
void loop()                             
{
  int irLeft = irDetect(9, 10, 42000);      
  int irRight = irDetect(2, 3, 42000);   
  if((irLeft == 0) && (irRight == 0))       
  {
    backward(1000);                     
    turnLeft(800);                     
  }
  else if(irLeft == 0)                       
  {
    backward(1000);                     
    turnRight(400);                  
  }
  else if(irRight == 0)                  
  {
    backward(1000);                     
    turnLeft(400);                       
  }
  else                                    
  {
    forward(20);                        
  }
}

int irDetect(int irLedPin, int irReceiverPin, long frequency)
{
  tone(irLedPin, frequency, 8);            
  delay(1);                              
  int ir = digitalRead(irReceiverPin);     
  delay(1);                             
  return ir;                             
}  

void forward(int time)                     
{
  servoLeft.write(1700);       
  servoRight.write(1300);      
  delay(time);                     
}

void turnLeft(int time)            
{
  servoLeft.write(1300);    
  servoRight.write(1300);     
  delay(time);
}

void turnRight(int time)            
{
  servoLeft.write(1700);   
  servoRight.write(1700);    
  delay(time);
}

void backward(int time)
{
  servoLeft.write(1300);
  servoRight.write(1700);
  delay(time);
}

2. 회로

https://github.com/jjang1597/IT/blob/master/Source/IR%201.jpg

3. 소감


