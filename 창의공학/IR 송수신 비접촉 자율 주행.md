# 아두이노 코드
```
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
```
# 회로

![IR](/Source/IR.jpg)
![IR회로](/Source/IR회로.jpg)

# 유튜브 링크
-   

# 소감

비접촉 자율주행하는 방법이 적외선을 이용할 것이라는 사실을 생각조차 못했는데 이용한다는 사실을 알고나니,  
암초 확인, 수심깊이 측정, 자율주행 자동차, 로봇 청소기 등 일상생활에서 물체를 감지할때  
적외선을 이용한다는 사실을 알게되었습니다.  
이를 통해 해당 기술들의 작동 원리를 조금 더 이해할 수 있었고, 아두이노의 실용성과,  
중요성을 깨닫게 되는 계기가 되었습니다.  
이렇게 실생활에서 이용되고 있는 적외선을 저희가 직접 이용한다는 것과,  
신기하고 새로운 내용을 배운다는 사실에 설레었습니다.  
또한, 팀원 몇몇이 이해 못하고 있는 상황에서 서로가 가르쳐 주면서 부족한 부분들을 채울수 있었습니다.  
몇부분의 코드를 제외하고 더듬이 주행 로봇이랑 코드가 비슷했는데,  
이번 과제를 통해 더듬이 주행 로봇을 복습함과 동시에 새로운 지식들도 습득할수 있었습니다.  
복습하면서 ABot으로 했던 내용들도 잊어버린 부분들이 많아 팀원들과 같이 카페를 찾아보고,  
손코딩도 5번씩 하며 완벽하게 복습하였습니다.  
특히 이렇게 팀원들과 직접 짠 코드들을 실제로 로봇을 통해 결과를 눈으로 확인할수 있어 뿌듯함이 배로 되었습니다.  
앞으로도 열심히 노력하여 ABot을 정복할수 있도록 노력하겠습니다 감사합니다 교수님! 창의공학 사랑합니다~
