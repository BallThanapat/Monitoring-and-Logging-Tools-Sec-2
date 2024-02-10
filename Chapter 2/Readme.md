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
