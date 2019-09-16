# Report
for my school study.


1. 시나리오 및 작성 소감.
조도센서를 통해 입력값을 받아, 그 입력값에 따라서 화면에 나오는 도형의 색깔을 바꾸는 프로그램을 배웠습니다.
실제로 코드가 응용 될 수 있다는 사실을 알고 흥미로웠습니다.


2. 아두이노 코드
void setup()

{

  Serial.begin(9600); // 1초에 9600비트씩 보낸다.

}

int a;

void loop()

{

  a = analogRead(A0);

  Serial.println(a);

  delay(500);

}


3. 프로세싱 코드
import processing.serial.*;

Serial p;

 

void setup()

{

  size(300,300);

  p=new Serial(this,"COM4",9600);

}

void draw(){

 if(p.available()>0){

   String m=p.readString();

   int a = int(m.trim());

   print(a);

   if(a>100) fill(0,255,0);

      else  fill(255,0,0);

   ellipse(150,150,150,150);

   }

}


4. 소감
교수님과 함께 짠 프로그램을 아두이노를 통해 실현시킬 수 있다는 사실을 깨닫고 관련 분야에 대해서 더 흥미를 느꼈습니다.
앞으로 쓸 센서와, 그에 대한 코드 및 내용에 대한 궁금증이 커졌습니다.
또한, 이를 통해 사물인터넷에 관한 이해도가 높아졌습니다.
이런 질 좋은 수업을 제공해 주시는 교수님께 감사드립니다!
