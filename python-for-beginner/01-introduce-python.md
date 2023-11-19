# แนะนำภาษา python

python เวอร์ชั่นปัจจุบัน คือ 3.6 (19 มิถุนายน 2560) เป็น high-level language มีการแปลภาษาแบบ interpreter คือทำทีละบรรทัด เป็นภาษาที่เรียนรู้ได้ง่าย

ในชีวิตประจำวัน python ถูกนำมาใช้งานหลายอย่าง เช่นการทำ back-end ของ dynamic website, ใช้ในงาน data science, การเขียนโปรแกรมลงบน hardware สำหรับงาน embedded system เป็นต้น\
สามารถดาวน์โหลด python มาใช้งานได้ที่ [https://www.python.org/downloads/](https://www.python.org/downloads/) และมี document วิธีการเขียนโปรแกรมด้วยภาษา python ที่ [https://docs.python.org/3/library/](https://docs.python.org/3/library/)

เราสามารถใช้ editor ในการเขียนโปรแกรมภาษา python ได้หลากหลายโปรแกรม เช่น notepad++, sublinetext, pyCharm เมื่อเราติดตั้งตัว python แล้ว ก็สามารถ run source code ภาษา python ได้

ความแตกต่างของ python 2.7 vs python 3.3 ถึงเวอร์ชั่นปัจจุบันจะเป็น python 3.x แต่มีบางโปรแกรมและบางหน่วยงานใช้ python 2.7 อยู่ ดังนั้นเราจะมาดูความแตกต่างกันระหว่าง 2 เวอร์ชั่นนี้

<table><thead><tr><th width="184.90899062327634"></th><th>python 2.7</th><th>python 3.x</th></tr></thead><tbody><tr><td>Print</td><td><code>print “hello world”</code></td><td><code>print (“hello world”)</code></td></tr><tr><td>Integer Division</td><td>3/2 = 1</td><td>3/2 = 1.5</td></tr><tr><td>Input Value</td><td><code>raw_input()</code></td><td><code>input()</code></td></tr><tr><td>Stripline in File</td><td><code>string.spilt(f.read(), “\n”)</code></td><td><code>f.read().strip().splitlines()</code></td></tr><tr><td>File Mode</td><td>rb, wb, ab</td><td>r+, w+, a+</td></tr></tbody></table>

การเลือกใช้ python ขึ้นอยู่กับโปรแกรมที่รองรับ และปัจจัยอื่นๆ ที่นอกเหนือจากความใหม่ของเวอร์ชั่น
