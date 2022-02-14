# ออกแบบการทดลอง
## โปรแกรมเปิดไฟทุก ๆ 19.00 น.
### ตัวอย่าง Code
#include <Arduino.h>

int cnt = 0;

void setup()
{
	Serial.begin(115200);
	pinMode(0, INPUT); //input from lux light meter
	pinMode(1, INPUT); //input from switch
	pinMode(2, OUTPUT);
	Serial.println("\n\n\n");
}

void loop()
{
    cnt++ ;
    
	int val = digitalRead(0);
	int switch = digitalRead(1);
	int hour = cnt/(1000*60*60) ;
	int time = hour % 24 ;
	bool night = time >= 19 ;

	if(switch == 1) {
		digitalWrite(2, HIGH);
	} else {
	    if(val==1 || night ) {
            digitalWrite(2, HIGH);
        } else {
            digitalWrite(2, LOW);
        }
	}
	delay(100);
}
### คำอธิบาย code
- Line1 = คำสั่งดึงข้อมูลจาก Aduino.h
- Line3 = ปรพกาศตัวแปร cnt
- Line5 = ส่งสัญญาณการตั้งค่าโปรแกรมเตรียมรัน
- Lin6-7
