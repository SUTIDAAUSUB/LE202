# ทบทวนความรู้เกี่ยวกับ ESP-01 microcontroller
## (1) Digital
: การเอาสัญญาณไฟฟ้ามาแทนด้วยเลขฐาน 2 โดยที่ ON "1" และ OFF "0" ข้อมูลDigital จะนำมาใช้โดยนำเลขฐานมาแทนตัวอักษร
## (2) Voltage
: คือความต่างศักย์ระหว่างจุดสองมี 2 ประเภทคือไฟฟ้ากระแสสลับ(AC) เช่น ไฟบ้าน และไฟฟ้ากระแสตรง(DC) เช่น แบตเตอรี่
## (3) Computer
: วิวัฒนาการมานานตั้งแต่มีขนาดเครื่องใหญ่จนมีขนาดเครื่องที่เล็กลง มีความเร็วมากขึ้น ความจุมากขึ้น ใช้งานได้ง่ายขึ้น
## (4) Internet
: ทำให้อุปกรณ์ต่างๆเชื่อมโยงกันง่ายขึ้นทั้งไร้สาย และมีสาย มีผู้ใช้มากในปัจจุบันเกิดเว็บไซต์ใช้งานเพิ่มมากขึ้นเรื่อย ๆ
## (5) Program Lang
: ซอฟแวร์เขียนโปรแกรม มีภาษาต่างๆมากมาย เช่น ภาษา C , Python , JAVA
## (6) Platfomio
: โปรแกรมบนคอมพิวเตอร์ชนาดเล็กเรียกว่า"microcontroller" มีผู็ผลิตมากมาย
## (7) Iotset 1
: การเตรียมการเพื่อพัฒนาไมโครคอนโทรเลอร์
1. เปิดเว็บ -> https://github.com/choompol-boonmee/iotset1
2. โหลดโปรแกรม git
3. เปิด command prompt -> รันคำสั่ง git clone มันจะโหลดสิ่งที่จำเป็นมาจาก internet
4. Run Python 3.91 และ Run pip install -u platformio
5.  เปิด command prompt -> cd iotset1/examples -> dir จากนั้นตรวจสอบโฟลเดอร์ ex01,ex02,ex03
6.  Run ตัวอย่างที่ 1 โดย cd iotset1/examples/ex01 -> pio run
7.  Run ตัวอย่างที่ 2 โดย cd iotset1/examples/ex02 -> pio run

# การทดลองบน ESP-01 จำนวน 6 การทดลอง
ตัวอย่างไมโครคอนโทรเลอร์์ ESP01 มี USB ต่อ โดยเราจะเขียนโปรแกรมใส่ไมโครคอนโทรเลอร์ที่มีwifiในตัวเองด้วย เช่น ใส่ EX1 ที่เขียนด้วยภาษา C++ ในแต่ละโปรแกรมเมื่อใช้ platformio จะมีชื่อไฟล์ว่า platformio.int ไว้บอกว่าเป็น platform ของบริษัทใด,บอร์ดอะไร,ใช้วิธีเขียนแบบไหน,ต้องต่อ port อะไร เมืื่อกด run และโหลดโปรแกรมเข้าไปในไมโครคอนโทรเลอร์ (มีความเร็วประมาณ115,200 bit/s) ใช้คำสั่ง upload โปรแกรมจะพร้อม Run ในไมโครคอนโทรเลอร์ เราจะใช้คำสั่ง pio device moniter
## (1) run example 1 
: รอดูผลลัพธ์์ที่แสดงผลออกมาจากคอมพิวเตอร์์จะเป็นการนับไปเรื่อย ๆ จาก 0 ถ้ากด reset จะเริ่มทำงานใหม่
## (2) run example 2 
: เมื่อดูผลลัพธ์บนคอมพิวเตอร์ โปรแกรม EX2 จะแสดง wifi แต่ละตัวที่ได้รับ
## (3) run example 3/1
: ตัวอย่างไมโครคอนโทรเลอร์ ESP01 จะมี outpput oprt และ input port อยู่ 2 พอร์ทคือ หมายเลข 0 และหมายเลข 1 เมื่อต้องการเขียนโปรแกรมลงไปเราจะนำตัวไมโครคอนโทรเลอร์ต่อกับ usb series port แต่เราจะใช้ adapter เสียบที่ usb series port อีกทีหนึ่ง เพื่อจะได้ใช้งาน port 0 และ 1 ด้วย และเมื่อลองอัพโหลดโปรแกรมลงไป ผลลัพธ์คือ โปรแกรมจะ set port 0 เป็น port output โดยถ้านับจำนวนครั้งเป็นเลขคี่ ให้ on และคู่ให้้ off โดย loop นับไปทุกครึ่งวินาทีพอดูผลรันผลจะแสดง on และ off สลับกันไปเรื่อยๆ ที่ LED ที่ต่อ port 0 ก็จะกระพริบ ส่วนอีก port จะไม่กระพริบ
## (3) run example 3/2
: เอา relay มาต่อเพื่อให้ port 0,1 ที่บังคับส่งสัญญานไปที่คอนโทรดีเลย์เพื่อใช้ เปิด-ปิด สวิตซ์ และนำ relay ไปต่อกับแหล่งจ่ายไฟ ไฟจะติดและกระพริบ และสามารถเปิดปิดได้
## (4) run example 4
: การเอา input ภายนอกเข้ามาในไมโครคอนโทรเลอร์ set port 0 input, port 2 output โปรแกรมจะอ่านข้อมูลจากพอร์ท 0 และแสดงผลเป็น read 1 ตลอดไฟดับ แต่เมื่อนำสายสีขาวไปต่อที่สายดำจะอ่านค่าเป็น 0 ไฟติดตามที่เราเขียนไว้ และเมื่อลองกดสวิตซ์ที่ต่อจาก EX3 เมื่อกดเปิดอ่าน 0 ไฟติด เมื่อลองต่อกับ sensor แสงไปต่อกับไฟเลี้ยง และต่อกับตัวต้านทานที่ port 0 และนำขาวอีกเส้นไปต่อกับกราวร์เส้นสีดำ และเมื่อไม่บังแสงไฟจะติดและมีค่า output เป็น 0
## (5) run example 5 
: โปรแกรมสร้างเว็บเซิฟเวอร์ผ่าน wifi setup จะconnect กับ wifi ที่เราเลือกไว้จากนั้น setup ตัว  server ถ้าการเชื่อมต่อจะแสดงผล hello และนับนับเรื่อย ๆ เมื่ออัปโหลดโปรแกรม และทดสอบโดยใช้เว็บบราวเซอร์ที่เข้าไปดูเว็บทั่วไปได้
## (6) run wifi AP
: เป็นโปรแกรมที่ใช้ wifi โดยสร้าง wifi เองใช้เอง เริ่มแรกตั้งชื่อ wifi และ รหัส ตอนปล่อยไวฟายเราต้องกำหนด IP Addrees และเตรียมเว็บไว้ setup ใส่ชื่อไวฟาย และ รหัส ลงไป แล้วใส่ IP ที่ตั้ง จากนั้นนโหลดโปรแกรมลงไป และลองใช้มือถือ ค้นหาไวฟาย ซึ่งก็จะสามารถเชื่อมได้ปกติ
