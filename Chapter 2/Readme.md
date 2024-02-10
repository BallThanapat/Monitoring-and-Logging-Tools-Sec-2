# Chapter 2 Log Reader/Analysis
## Log Reader/Analysis มันคืออะไร?
   **Log Analysis**  เป็นกระบวนการตรวจสอบ วิเคราะห์การบันทึก(logs) เพื่อตรวจดูพฤติกรรมของโปรแกรม และคาดการณ์ปัญหาที่อาจจะเกิดขึ้นจากการใช้งาน

## คำสั่งพื้นฐานสำหรับ Log Analysis
### Journalctl
   **Journalctl** - เป็นส่วนหนึ่งของชุดยูทิลิตี้ systemd และใช้เพื่อค้นหาและแสดงข้อความบันทึกจาก Systemd Journal(ระบบการบันทึกแบบรวมศูนย์ที่รวบรวมและจัดเก็บข้อมูลบันทึกจากแหล่งต่างๆ รวมถึงบริการของระบบ เหตุการณ์เคอร์เนล และแอปพลิเคชันผู้ใช้)

#### Syntax ของคำสั่ง journalctl
	journalctl [options] [unit]

#### ตัวอย่างเมื่อใช้คำสั่ง journalctl
<div>
  <img align="center" width="80%" src="image/journalctl.png">
</div>

#### Option และ Command ทั้งหมดของคำสั่ง journalctl
- 📚 [**การใช้และคำอธิบายเบื้องต้นของ Option&Command ทั้งหมดของคำสั่ง journalctl**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%202/Op%26Com_Journalctl/Readme.md)

### Dmesg
   **dmesg** มาจาก divide message มอบวิธีที่สะดวกในการตรวจสอบเคอร์เนลริงบัฟเฟอร์ ซึ่งจัดเก็บข้อความที่สร้างโดยเคอร์เนลระหว่างกระบวนการบู๊ตและในขณะที่ระบบกำลังทำงาน ข้อความเหล่านี้มีข้อมูลสำคัญเกี่ยวกับการตรวจหาฮาร์ดแวร์ การเริ่มต้นอุปกรณ์ และปัญหาที่อาจเกิดขึ้นกับเคอร์เนล

#### Syntax ของคำสั่ง dmesg
	sudo dmesg [options]
  **จำเป็นต้องใช้สิทธิ์ root ในการใช้คำสั่ง

#### ตัวอย่างเมื่อใช้คำสั่ง dmesg
<div>
  <img align="center" width="80%" src="image/dmesg.png">
</div>

#### Option และ Command ทั้งหมดของคำสั่ง dmesg
- 📚 [**การใช้และคำอธิบายเบื้องต้นของ Option&Command ทั้งหมดของคำสั่ง dmesg**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%202/Op%26Com_dmesg/Readme.md)

### Last
   **last** ใช้เพื่อแสดงรายการผู้ใช้ทั้งหมดที่เข้าสู่ระบบและออกจากระบบตั้งแต่ไฟล์ `/var/log/wtmp` ถูกสร้างขึ้น สามารถกำหนดชื่อผู้ใช้ตั้งแต่หนึ่งรายการขึ้นไปเป็นอาร์กิวเมนต์เพื่อแสดงเวลาเข้าสู่ระบบเข้า (และออก) และชื่อโฮสต์

#### Syntax ของคำสั่ง last
	last [options] [username...] [tty...]

#### ตัวอย่างเมื่อใช้คำสั่ง dmesg
<div>
  <img align="center" width="80%" src="image/last.png">
</div>

#### Option และ Command ทั้งหมดของคำสั่ง last
- 📚 [**การใช้และคำอธิบายเบื้องต้นของ Option&Command ทั้งหมดของคำสั่ง last**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%202/Op%26Com_Last/Readme.md)

### Lastcomm
   **lastcomm** ให้ข้อมูลเกี่ยวกับคำสั่งที่ดำเนินการก่อนหน้านี้ Lastcomm ที่ไม่มีอาร์กิวเมนต์จะแสดงข้อมูลเกี่ยวกับคำสั่งทั้งหมดที่บันทึกไว้ระหว่างอายุการใช้งานของไฟล์การบัญชีปัจจุบัน ต้องรันคำสั่ง sudo apt  install acct เพื่อติดตั้งก่อนจึงจะสามารถรันคำสั่ง Lastcomm ได้ 

#### Syntax ของคำสั่ง lastcomm
	lastcomm [ -X ][ Command ] [ Name ] [ Terminal ]

- Command คำสั่งที่ระบุโดยพารามิเตอร์ 
- Name คำสั่งที่ดำเนินการโดยผู้ใช้ที่ระบุโดยพารามิเตอร์ 
- Terminal คำสั่งจากเทอร์มินัลที่ระบุโดยพารามิเตอร์ เทอร์มินัลสามารถตั้งชื่อแบบเต็มหรือย่อเป็น tty ตัวอย่างเช่น คุณสามารถระบุเทอร์มินัล tty0 หรือเทอร์มินัล 0 ได้


#### ตัวอย่างเมื่อใช้คำสั่ง lastcomm
<div>
  <img align="center" width="80%" src="image/lastcomm.png">
</div>

#### ในแต่ละ process จะปรากฏสิ่งเหล่านี้
- ชื่อของผู้ใช้ที่รันกระบวนการ
- แฟล็กใดๆ ที่เกี่ยวข้องกับการบัญชีที่รวบรวมเมื่อคำสั่งดำเนินการ ต่อไปนี้เป็นแฟล็กที่ถูกต้อง:
<div align="center" style="width: 100%; margin: auto;">
<table style="width: 100%; border-collapse: collapse;">
	
| Item | Description |
|  S   | Root ดำเนินการคำสั่ง |
|  F   | คำสั่งรันตามทางแยก แต่ไม่มีรูทีนย่อยต่อไปนี้ |
|  C   | คำสั่งทำงานในโหมดความเข้ากันได้ของ PDP-11 |
|  D   | คำสั่งสิ้นสุดลงด้วยการสร้างไฟล์หลัก |
|  X   | คำสั่งถูกยกเลิกโดยมีสัญญาณ |
</table>
</div>

- ชื่อของคำสั่งที่ใช้เรียกกระบวนการ
- วินาทีของเวลา CPU ที่ใช้โดยกระบวนการ
- เวลาที่กระบวนการเริ่มต้นขึ้น

#### Option และ Command ทั้งหมดของคำสั่ง lastcomm
- 📚 [**การใช้และคำอธิบายเบื้องต้นของ Option&Command ทั้งหมดของคำสั่ง lastcomm**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%202/Op%26Com_Lastcomm/Readme.md)
