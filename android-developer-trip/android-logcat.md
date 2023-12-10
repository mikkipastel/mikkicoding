# Android Logcat

<figure><img src="../.gitbook/assets/image (2) (1).png" alt="" width="563"><figcaption></figcaption></figure>

Logcat บน Android Stuio ถูกเปลี่ยนหน้าตาไปในเวอร์ชั่น Dolphin | 2021.3.1 ซึ่งสามารถสร้างได้หลาย ๆ logcat windows ด้วยกันเนอะ

ส่วนประกอบของ logcat คร่าว ๆ ก็จะมี date แสดงวันที่และเวลา, tag ว่ามันมาจากไหน, package ก็คือมาจากแอพไหนแหละ, log level, message

แล้วตรงช่อง filter เราสามารถใส่อะไรได้บ้าง ไปดูกัน

* tag: ใส่ tag ที่เราต้องการ filter เช่น `tag:System.out`
* package: เลือก package name ที่เราต้องการ เช่นดูแค่แอพตัวเองก็ `package:mine`
* process: เลือก process name ที่เราต้องการ แต่ไม่ค่อยได้ใช้แหะ
* message: message จาก log ที่เราต้องการ เช่น `message:sendrequest`
* level: log level ที่เราอยากได้ โดยทั้งหมดจะมี Verbose (`V`, มี priority ตํ่าสุด), Debug (`D`), Info (`I`), Warning (`W`), Error (`E`), Fatal (`F`), Silent (`S` ,มี priority สูงสุด ซึ่งมันจะไม่พิมพ์อะไรออกมา) เช่นอยากดู error ก็ใส่ `level:error`
* age: เราอยากได้ logcat ล่าสุดเมื่อกี่วินาที (`s`) หรือกี่นาที (`m`) หรือกี่ชั่วโมง (`h`) หรือกี่วัน (`d`) เช่นอยากได้ log เมื่อ 5 นาทีที่ผ่านมา ก็ใส่ `age: 5m`
