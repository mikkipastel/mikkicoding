# แนะนำภาษา python

python เวอร์ชั่นปัจจุบัน คือ 3.6 (19 มิถุนายน 2560) เป็น high-level language มีการแปลภาษาแบบ interpreter คือทำทีละบรรทัด เป็นภาษาที่เรียนรู้ได้ง่าย

ในชีวิตประจำวัน python ถูกนำมาใช้งานหลายอย่าง เช่นการทำ back-end ของ dynamic website, ใช้ในงาน data science, การเขียนโปรแกรมลงบน hardware สำหรับงาน embedded system เป็นต้น\
สามารถดาวน์โหลด python มาใช้งานได้ที่ [https://www.python.org/downloads/](https://www.python.org/downloads/) และมี document วิธีการเขียนโปรแกรมด้วยภาษา python ที่ [https://docs.python.org/3/library/](https://docs.python.org/3/library/)

เราสามารถใช้ editor ในการเขียนโปรแกรมภาษา python ได้หลากหลายโปรแกรม เช่น notepad++, sublinetext, pyCharm เมื่อเราติดตั้งตัว python แล้ว ก็สามารถ run source code ภาษา python ได้

ความแตกต่างของ python 2.7 vs python 3.3 ถึงเวอร์ชั่นปัจจุบันจะเป็น python 3.x แต่มีบางโปรแกรมและบางหน่วยงานใช้ python 2.7 อยู่ ดังนั้นเราจะมาดูความแตกต่างกันระหว่าง 2 เวอร์ชั่นนี้

|                   | python 2.7                     | python 3.x                      |
| ----------------- | ------------------------------ | ------------------------------- |
| Print             | `print “hello world”`          | `print (“hello world”)`         |
| Integer Division  | 3/2 = 1                        | 3/2 = 1.5                       |
| Input Value       | `raw_input()`                  | `input()`                       |
| Stripline in File | `string.spilt(f.read(), “\n”)` | `f.read().strip().splitlines()` |
| File Mode         | rb, wb, ab                     | r+, w+, a+                      |

การเลือกใช้ python ขึ้นอยู่กับโปรแกรมที่รองรับ และปัจจัยอื่นๆ ที่นอกเหนือจากความใหม่ของเวอร์ชั่น
