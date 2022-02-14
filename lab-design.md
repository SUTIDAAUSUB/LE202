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
- Line6-7 = เป็นคำสั่งที่ตั้งค่าให้คอมเชื่อมต่อกับ microcontroller
- Line8 = ตั้งค่า port 0 เป็น input
- Line9  = ตั้งค่า port 1 เป็น input
- Line10 = ตั้งค่า port 2 เป็น output
- Line11 = สั่ง print เว้นบรรทัดไป 3 บรรทัด
- Line14 = คำสั่ง loop
- Line15-16 = คำสั่งให้นับ cnt เพิ่มขึ้น
- Line18 = set ให้ val รับค่า input จาก port 0
- Line19 = set ให้ switch รับค่า input จาก port 0
- Line20 = กำหนดตัวแปร hour คือ cnt/(1000*60*60)
- Line21 = กำหนดตัวแปร time คือการเอา hour มาหาเศษจากการหาร 24
- Line22 = กำหนดตัวแปร night ถ้า >= 19 เป็น T, < เป็น F
- Line24-34 = set สวิตซ์ถ้า = 1 เปิดไฟ ถ้าไม่ใช่ไฟจะไม่ิตด
- Line36 = คำสั่ง Delay ให้ loop ทุกๆ 0.1 วินาที
