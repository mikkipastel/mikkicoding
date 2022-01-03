# Loop Statement

ใน python มี for และ while ในการใช้วนลูป

มาลองทำดูดีกว่า พิมพ์ค่าสมาชิกแต่ละตัวใน `array_list`ซึ่งในภาษา python จะต่างจากภาษาอื่นๆ สามารถวนลูปค่าใน list ได้เลย ภาษาอื่นๆจะวนจากตัวเลข เช่น

```
array_list = [‘apple’, ‘papaya’, ’banana’, ’orange’]
for i in array_list:
   print (i)
```

ให้พิมพ์เลข 1-10 ออกมาสู่หน้าจอ สามารถเขียนได้ดังนี้

```
#print 1-10
i=1
while i <= 10:
    print(i)
    i += 1
```

function range เป็น function ที่สร้าง range ค่าในช่วงที่เราต้องการ เช่น `range(10)` สร้างค่าเริ่มจาก 0 ไป 10 ตัว ดังนั้นจะได้ค่า 0-9 เราไม่สามารถเขียนเป็นเลขโดดๆใน for ได้

```
#print 1-10
for i in range(1,11):
   print (i)
```

#### loop comprehensions <a href="#loop-comprehensions" id="loop-comprehensions"></a>

คือการเขียน loop statement แบบลดรูป พร้อมการเปรียบเทียบค่า ตัวอย่าง เช่น หาเลขระหว่าง 0-30 ที่หารด้วย 2 ลงตัว

ถ้าเราจะเขียนแบบเต็มๆ จะได้แบบนี้ ข้อดี คือ สามารถตรวจสอบได้เวลาที่โค้ดเรามีปัญหา

```
evens = []
for i in range(31):
   if i % 2 == 0:
      evens.append(i)
```

และการเขียนแบบลดรูปแบบ loop comprehensions

```
evens = [i for i in range(31) if i % 2 == 0]
```
