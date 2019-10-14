1. 소스코드

#include <Servo.h>
Servo sr, sl;
void setup() {
  Serial.begin(9600);
  sr.attach(13); sl.attach(12);
}

void loop() {
  if (Serial.available()) {
    char b[2];
    int p, r;
    Serial.readBytes(b, 2);
    p = b[0] * 3; 
    r = b[1];       
    sr.write(1500 + p - r);
    sl.write(1500 - p - r);
    Serial.write('1');
  }
}


2. 구동화면
![1](/Source/1.jpg)
![1](/Source/2.jpg)
![1](/Source/3.jpg)


3. 소감
