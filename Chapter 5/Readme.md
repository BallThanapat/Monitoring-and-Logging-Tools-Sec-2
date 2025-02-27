# Chapter 5 Working With Text
การทำงานกับข้อความในlinux เกี่ยวข้องกับการจัดข้อมูลเพื่อเอาข้อมูลมาใช้หรือแปลงเป็นเอาต์พุตที่ต้องการ ในlinuxทุกอย่างถือว่าเป็นไฟล์รวมถึงข้อความด้วย การที่เรามีพื้นฐานการใช้คำสั่งต่างๆที่เกี่ยวกับการประมวลผลช้อความในlinuxทำให้ สามารถทำงานเสร็จได้และมีประสิทธิภาพอย่างมากและช่วยประหยัดเวลาในการแก้ไขปัญหาจากงานที่ยากและน่าเบื่อสามารถแก้ไขได้ภายในไม่กี่วินาที<br>
**Working with text ใน linux แบ่งได้หลากหลายประเภทเช่น**<br>
## Component ต่างๆ<br>
**1. การจัดการไฟล์**<br>
การจัดการไฟล์ในLinuxหัวใจสำคัญในการใช้งานระบบ
การจัดการไฟล์ในระบบปฏิบัติการ Linux นั้นหมายถึงกระบวนการควบคุมดูแลและจัดระเบียบไฟล์ข้อมูลโปรแกรมบนระบบLinuxเปรียบเสมือนกุญแจสำคัญที่ช่วยให้ผู้ใช้สามารถใช้งานระบบได้อย่างมีประสิทธิภาพปลอดภัยและสะดวก<br>
* การสร้างและลบไฟล์<br>
* การอ่านและเขียนเนื่อหาในไฟล์<br>
* การค้นหาข้อความในไฟล์<br>
* การแก้ไขไฟล์์<br>

**2. การแปลงข้อความ**<br>
แปลงข้อความในlinuxมีความจำเป็นอย่างมาก เพราะหลังจากที่เราได้ทำการแก้ไขแล้วอาจจะมีข้อผิดพลาด/บกพร่องบางอย่าง คำสั่งการแปลงข้อความใน linux จึงมีความสำคัญไม่แพ้กับการแก้ไขไฟล์ เพื่อช่วยในการ format ไฟล์ให้อยู่ในกรอบที่เราวางเอาไว้
เช่น ถ้าเราพิมตัวอักษรในไฟล เป็น ภาษาอังกฤษ ตัวพิมเล็ก แต่เราดันเปลี่ยนใจ อยากได้ ไฟล ตัวพิมใหญ่ทั้งหมด เราก้สามารถใช้ คำสั่งแปลงข้อความของlinux ในการแก้ปัญหาแทนการไปนั้ง ใช้ vim แก้ไข ข้อความทั้งหมดได้ โดยใช้แค่ คำสั่ง tr เดียวเรามาเรียนรู้
ประเภทต่างๆของการแปลงข้อความในlinux กันนะงับผม<br>
* การแปลงรูปแบบตัวอักษร<br>
* การแปลงรูปแบบไฟล์<br>

**3. การกรองข้อความ**<br>
การกรองข้อความในlinux คือการที่เราอยากได้ข้อความแค่บางส่วนที่ต้องการ และละทิ้งส่วนที่เราไม่ต้องการออก อย่างเช่น อยากได้แค่ 3บรรทัดบนสุด ใช้head อยากได้ 3บรรทัดล่างสุดเราใช้ tail ก็คิอกรองข้อความเพิ่อให้เราไม่ต้องไปหาจากในไฟลเองซึ่งลดความยุ่งยากได้มากเลย<br>
* การกรองตามเงื่อนไข<br>
* การเรียงลำดับข้อความ<br>





### การจัดการไฟล์(Managing File)
อย่างที่กล่าวไปการจัดการไฟล์มีบทบาทเกี่ยวกับการเข้าถึงข้อมูล จัดระเบียบข้อมูล จัดการพิ้นที่สำหรับเก็บข้อมูล สำรองข้อมูล รวมๆแล้วเน้นไปทางสร้างข้อมูลเพื่อนำมาใช้ต่อในภายภาคหน้าได้<br>
เรามาเรียนรู้พื้นฐานเกี่ยวกับ การการสร้างและลบไฟล์ ในlinuxกันดีกว่า<br>
**1. เริ่มต้นด้วยการสร้างไฟล**
ก่อนที่จะสร้างไฟล์เราต้องรู้ก่อนว่าตอนนี้เราอยู่ที่ไหนในระบบ<br>
ใช้ Command `PWD`<br>
หลังใช้จะบอกว่าเราอยุ่ ณ จุดใดในระบบ<br>
Command การ สร้างfolder/directory แรก `mkdir`<br>
ใช้ `mkdir` ตามด้วยชื่อdirectoryที่อยากตั้้ง
ตัวอย่างเช่น<br>
                
 mkdir popo1

จะเป็นการสร้าง directory ชื่อ popo1 มา
หากเราใช้คำสั่ง ls ดู Directory ในไฟล์นั้นๆจะพบว่า directory ได้ถูกสร้างขึ้นแล้ว
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/a6b39d8d-6b41-4c3c-9e26-bf450a2f04a5)<br>
**Trick เลฺ็กๆน้อยๆ**<br>
เราสามารถสร้างdirectoryได้ หลายๆอันในทีเดียวเช่นกันเช่น
**codeเดียวแก้** mkdir popo1 popo2 popo3
เราได้จะได้ไม่ต้องพิมหลายๆรอบเสียเวลา<br>
แต่หากเรามีไฟล์ชื่อนั้นอยู่แล้ว คำสั่งจะข้ามไป สร้างDirectory อันที่เหลือเลย<br>
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/0a259530-2d95-42ec-9012-34c35bd56369)<br>
หากเราต้องการสร้าง Directory ซ้อนใน Directory อีกทีนึง เราสามารถ ใช้ `/` ในการ เจาะลึกลงไปได้เช่น<br>
mkdir popo1/popoinside/popoinsideinsidee<br>
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/170e2357-07ed-43e5-9fe8-65b8ccd64328)<br>
จะเห็นได้ว่า ข้างใน `popo4` จะมี directory `popoinside` และ `popoinside` จะมี Directory `popoinsidee` อีกทีนึง<br>
**มาถึงการลบ กันบ้าง**<br>
ถ้าตอนไหนเราอยากลบDirectoryใน linux เราสามารถใช้คำสั่ง `rm -r`ในการลบได้ หรือ`rmdir` <br>
ตัวอย่าง<br>
rm -r popo1<br>
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/1b1197c4-f72a-4fe7-b0b2-83fd4a631dbc)<br>
จากที่มี Directory popo1ก็จะหายไป<br>
หากต้องการลบ Directory ที่ว่างเปล่าไม่มีอะไรข้างในใช้ `rm -d`<br>
ตัวอย่าง<br>
ณ ตอนนี้เรามีDirectory เหลือ 4 อัน nopbys popo2 popo3 popo4<br>
ใช้คำสั่ง<br>
rm -d popo4<br>
จะเห็นได้ว่า จะไม่สามารถลบได้เพราะข้างใน popo4 ยังมี content ข้างในอยุ่ นั้นก็คือ popoinside<br>
แต่ถ้าใช้คำสั่ง<br>
rm -d popo2<br>
จะลบ Directory ได้ทันที<br>
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/e8bb8f37-749a-4c0d-80da-3145efc9ac7a)<br>
**ข้อควรระวัง**<br>
การลบนั้นถ้าเราลบแล้วอาจจะหายไปเลยแต่มีคำสั่งนึงช่วย ย่นการลบให้อีกstep ทำให้ เวลาเราเผลอลบอันไหนแล้วเราใส่คำสั่งนี้ไปมันจะให้เรายืนยันก่อนที่จะลบจะได้ไตร่ตรอง ว่าเราจะลบอันนี้แน่ๆใช้ไหม นั้นก็คือคำสั่ง<br>
`-vi`<br>
มันจะยืนยันก่อนว่าเราจะลบจริงๆใช้ไหม พิม y เพื่อ yes พืม n เพื่อ No<br>
**การสร้างไฟล์เปล่าๆ**<br>
ง่ายๆเราใช่คำสั่ง touch ตามด้วยชื่อไฟล์ เพื่อสร้างไฟล์<br>
ยกตัวอย่าง<br>
touch gumball<br>
จะได้ไฟล์ชื่อ gumball แบบในรูปเลย<br>
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/1377ace3-0fc5-4aac-b945-2250694ace9e)<br>
**การลบไฟล์**<br>
ลบง่ายมาแค่ใช้คำสั่ง rm ตามด้วยชื่อไฟล์จะลบทันที เช่น เราอยากลบ gumball เราใช้คำสั่ง<br>
rm gumball<br>
![image](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/assets/118421368/b2c83a57-57d3-40fb-a0a9-17935260926e)<br>

**2. มาต่อกันที่การอ่านและเขียนเนื้อหาไฟล์**<br>










ลิ้ง
https://earthly.dev/blog/linux-text-processing-commands/

# Other Chapter
- 🛠 [**Introduction Monitoring and Logging Tools**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/README.md)
- 🛠 [**Chapter 1 Monitoring and Logging Tools**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%201/Readme.md)
- 📈 [**Chapter 2 Log Reader and Analysis**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%202/Readme.md)
- 📝 [**Chapter 3 Log Collection and Server**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%203/Readme.md)
- 📚 [**Chapter 4 Log Files**](https://github.com/Jxwgame/Monitoring-and-Logging-Tools-Sec-2/blob/main/Chapter%204/Readme.md)

# Source
