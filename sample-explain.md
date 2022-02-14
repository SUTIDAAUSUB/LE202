# อธิบายโปรแกรม
## LAB1 การเขียนโปรแกรมเพื่อนรันบน Microcontroller
 - Line1 = คำสั่งให้ดึงข้อมูลจากไฟล์ Aduino.h มาใช้
 - Line3 = คำสั่งประกาศตัวแปร cnt
 - Line5 = ส่งสัญญาณการตั้งค่าโปรแกรมเตรียมรัน
 - Line6-8 = คำสั่งที่ตั้งค่าให้คอมพิวเตอร์เชื่อมกับ microcontroller
 - Line10-17  = คำสั่งloop
 - Line12 = คำสั่งให้เพิ่มค่าตัวแปรcnt โดยการนับcnt ไปเรื่อย ๆ
 - Line13 = ตั้งค่าให้print'PATTANI:cnt'
 - ผลลัพธ์:
## LAB2 การเขียนโปรแกรมค้นหา Wifi
- Line1-2 = คำสั่งให้ดึงข้อมูลจากไฟล์ Aduino.h และ ESP8266Wifi.h
- Line4 = คำสั่งประกาศตัวแปร cnt
- Line6 = ส่งสัญญาณการตั้งค่าโปรแกรมเตรียมรัน
- Line7-8 = คำสั่งที่ตั้งค่าให้คอมพิวเตอร์เชื่อมกับ microcontroller
- Line9-13 = ตั้งโหมด Wifi,สั่งให้ Wifi หยุดเชื่อมต่อ และสั่ง print เว้นบรรทัดไป3บรรทัด
- Line15-30 = print "เริ่มต้อนแสกนหา Wifi", คำสั่งให้โปรแกรมแสกนหาnetwork ถ้าเจอWifi จะprint ข้อมูลWifiทั้งหมดที่เจอ แต่ถ้าไม่เจอ print"NO NETWORK FOUND"
- Line33-34 = คำสั่งเว้นบรรทัด และคำสั่งDelayเพื่อค้นหาไวฟายใหม่ทุก ๆ 10 วินาที
-  ผลลัพธ์:
## LAB3 การเขียนโปรแกรม Output สัญญาณ Digital
- Line1-2 = คำสั่งให้ดึงข้อมูลจากไฟล์ Aduino.h และ ESP8266Wifi.h
- Line4 = คำสั่งประกาศตัวแปร cnt
- Line6 = ส่งสัญญาณการตั้งค่าโปรแกรมเตรียมรัน
- Line7-8 = คำสั่งที่ตั้งค่าให้คอมพิวเตอร์เชื่อมกับ microcontroller
- Line9 = setให้พอร์ท 0 เป็น output
- Line10 = สั่ง print เว้นบรรทัดไป3บรรทัด
- Line13-24 = คำสั่ง ถ้า cnt เป็นเลขคี่ print 'ON' ถ้า cnt เป็นเลขคู๋ print 'OFF' โดยที่จะloopใหม่ทุก ๆ 0.5 วินาที
-  ผลลัพธ์:
## LAB4 การเขียนโปรแกรม Input สัญญาณ Digital
- Line1-2 = คำสั่งให้ดึงข้อมูลจากไฟล์ Aduino.h และ ESP8266Wifi.h
- Line4 = คำสั่งประกาศตัวแปร cnt
- Line6 = ส่งสัญญาณการตั้งค่าโปรแกรมเตรียมรัน
- Line7-8 = คำสั่งที่ตั้งค่าให้คอมพิวเตอร์เชื่อมกับ microcontroller
- Line9 = set ให้พอร์ท 0 เป็น input
- Line10 = set ให้พอร์ท 2 เป็น output
- Line11 = สั่ง print เว้นบรรทัดไป3บรรทัด
- Line14-23 = set ให้ val รับค่า input จากพอร์ท 0 สั่ง print ค่าที่อ่านได้ ถ้าอ่านได้ 1 output = low แต่ถ้าอ่านได้ 0 output = high และ Delay 0.1 วินาที ก่อนเริ่ม loop ซ้ำ
-  ผลลัพธ์:
## LAB5 การเขียนโปรแกรมเชื่อมต่อ Wifi และ webserver
- Line1-2 = เชื่อมWifi และ server
- Line5-6 = ประกาศตัวแปรเก็บ SSID กับ Password
- Line8 = ตั้งค่า Server
- Line10 = คำสั่งประกาศตัวแปร cnt
- Line12-20 = ตั้งโหมด Wifi เป็น STA เชื่อมต่อ Wifi ด้วย SSID กับ Password ในตอนแรก Check Wifi ว่าเชื่อมต่อหรือยังทุก ๆ 5 วินาที หากยังไม่เชื่อมจะ print จุดออกมาเรื่อย ๆ
- Line21-22 = print IP Address
- Line24-26 = ถ้าไม่เชื่อมต่อ print' Path Not Found '
- Line28-48 = ถ้าเชื่อมต่อแล้ว print' Hello : cnt '
- Line50-51 = คำสั่งเรื่ม start server และ print 'HTTP Server Started'
- Line54-56 = ให้ Server เตรียมรับคำสั่ง และ loop เรื่อยๆ
-  ผลลัพธ์:
## LAB6 การเขียนโปรแกรมสร้าง Wifi แอคเชสพอยต์ (Wifi AP)
- Line1-2 = เชื่อมWifi และ server
- Line5-6 = ประกาศตัวแปรเก็บ SSID กับ Password
- Line8-10 = ตั้งค่า IP Address
- Line12 = ตั้งค่า Server
- Line14 = คำสั่งประกาศตัวแปร cnt
- Line16-17 = คำสั่งที่ตั้งค่าให้คอมพิวเตอร์เชื่อมกับ microcontroller
- Line19-20 = ตั้งค่า SSID , Password และค่าอื่น ๆ ตามตัวแปรที่กำหนดไว้
- Line23-25 = ถ้าไม่เชื่อมต่อ print' Path Not Found '
- Line27-32 = ถ้าเชื่อมต่อแล้ว print' Hello : cnt '
- Line34-35 = สั่งให้ Start Server และ print 'HTTP Server Started'
- Line38-40 = ให้ Server เตรียมรับคำสั่ง และ loop เรื่อยๆ
-  ผลลัพธ์:
