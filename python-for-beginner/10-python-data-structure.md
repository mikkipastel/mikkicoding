# Data structure

### Tuple

เราสามารถเก็บข้อมูล data type ใดก็ได้ ในตัวแปร tuple

```
t = 12345, 54321, 'hello!'
```

การ update ค่าใน tuple : `t[0] = 0`

เราสามารถนำ tuple นำมาบวกกันได้ด้วยนะ : `t3 = t1 + t2`

การลบค่าทั้งหมดใน tuple : `del t`

### Set

* union => `a | b`
* intersection => `a & b`
* difference => `a-b`, `b-a`
* symmetric difference => `a ^ b`

### Dictionary

การแสดงผลค่า key และ value ของสมาชิกแต่ละตัวใน dict

```
for key, val in num.items():
 print (key, val)
```

การเรียงค่า key ของ dict โดย output จะเป็น list `sorted(num)`

การเรียงค่า key และ value ของ dict โดย output จะเป็น list เช่นกัน `sorted(num.value)`

สำหรับการ sort by key และแสดง member ทั้งหมดใน dict ออกมา จะได้ output เป็น tuples นะ `sorted(num.items(), key=lambda x:x[1])`
