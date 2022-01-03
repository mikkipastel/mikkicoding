# Condition Statement

ใน python มี if-else ในการเลือกการตัดสินใจ มี syntax ดังนี้

* แบบทางเดียว

```
if (consition):
  <statement>
```

* แบบสองทาง

```
if (consition):
  <statement>
else:    
  <statement>
```

* แบบหลายทาง

```
if (condition):
  <statement>
elif (condition):   
  <statement>
else:    
  <statement>
```

#### มาลองทำดูดีกว่า

เขียนโปรแกรมตัดเกรดกันเถอะ ...

การตัดเกรดของวิชาการเรียน python พื้นฐาน มีเกณฑ์ ดังนี้

100 = A+, >=80 = A, >=70 = B, >=60 = C, >=50 = D, other = F

มาลงโค้ดดิ้งกัน

ให้ input มีชื่อตัวแปรว่า score และ output ชื่อว่า `grade`

```
# input student score
score = 78

if (score == 100):
  grade = "A+"
elif ((score >= 80) and (score < 100)):
  grade = "A"
elif ((score >= 70) and (score < 80)):
  grade = "B"
elif ((score >= 60) and (score < 70)):
  grade = "C"
elif ((score >= 50) and (score < 60)):
  grade = "D"
else:
  grade = "F"

print (grade)
```
