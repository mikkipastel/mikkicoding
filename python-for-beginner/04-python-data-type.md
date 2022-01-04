# Data type และการประกาศตัวแปร

Data type ใน python ไม่ได้มียุ่บยับหรือภาษาอื่น หลักๆมีสามตัวคือ

### Number

ตัวเลขทั้งหลาย เราจะบวกลบคูณหารผ่าน python ก็ทำได้ง่าย สบายๆเลย เช่น

```python
บวก ลบ คูณ หาร : +, -, *, /          =>    7/2
การหารเอาเศษ  : mod %               =>    7/2
เลขยกกำลัง     : power **            =>    7**2
การหารแบบปัดลง : floor division //   =>    7//2
การหารแบบปัดขึ้น : round()             =>    round(7/2)
```

ตัวอย่าง

```python
2^n - 1 จะได้เป็น (2**n)-1
pi r^2 จะได้เป็น pi*(r**2)
```

ตัวแปรประเภท Number ประกาศ data type เป็น เลขจำนวนเต็ม `int()` และ จำนวนทศนิยม `float()`

หรือประกาศเป็นเลขฐานต่างๆก็ได้ด้วยนะ เช่น เลขฐานสอง `bin()` เลขฐานสิบหก`hex()`

ตัวอย่าง

```python
int(‘11001100’,2) #204 แปลงเลขฐานสองเป็นฐานสิบ
int(‘0x20’,16) #32 แปลงเลขฐานสิบหกเป็นฐานสิบ
bin(int(‘0xDEC’,16)) #แปลงเลขฐานสิบหกเป็นฐานสิบ และแปลงเป็นเลขฐานสอง
hex(int(‘101010101010’,2)) #0xAAA แปลงเลขฐานสองเป็นฐานสิบ และแปลงเป็นเลขฐานสิบหก
```

การทำ Fixed point number

```python
from decimal import Decimal
interest = Decimal(“6.4200”)
```

### String

ตัวอักษร พี่เหลือมสามารถเล่นได้เยอะแยะเลย ทั้งการเลือกตัวอักษร ตัดทิ้ง บวกสตริง เซ็คความยาว

* การสร้างตัวแปร string ใหม่ : `hello = str()`
* การตรวจสอบความยาวของ string : `len(hello)`ถ้าความยาวเป็น 0 นั่นคือเป็นตัวแปร string เปล่าๆ นั่นเอง
* ค้นหาคำที่เราต้องการในตัวแปร string : `find()`
* การนำ space หัวท้ายออกจากกัน : `strip()`
* การตัดคำออกตามที่เราต้องการ : `split()`
* การแทนค่าคำ : `replace()`

#### ช่วงลองทำดู

เนื่องจากมันเล่นได้หนุกหนาน เลยมีอะไรให้ลองทำนิดหน่อย

1. ให้ตัวแปร string ชื่อว่า hello แล้วกัน มีค่า `Hello, it's me. I was wondering if after all these years`
2. ตรวจสอบความยาวของ hello
3. หาคำว่า me ใน hello
4. ตัดคำจาก space ออกเป็นคำๆ
5. แทนค่าคำว่า me ว่า you

<details>

<summary><strong>คำเฉลย</strong></summary>

```python
hello = "Hello, it's me. I was wondering if after all these years"
len(hello)
hello.find("me")
hello.split(" ")
hello.replace("me","you")
```

</details>

เราสามารถใช้ escaped with backslashes (\n \r\n \t \0 \x) ใน python ได้ด้วยนะ

### List

อันนี้อาจจะต่างจากพวกภาษา C แต่ภาษาอื่นๆก็มี มันคล้ายๆ array แต่ไม่ใช่ซะทีเดียว

```python
list = [1, 2, ,3, ...]
```

การใส่ค่าใน list ไม่จำเป็นต้องใส่ค่าประเทภเดียวกัน เช่น

```python
member = [“brown”, 94, True]
```

การเพิ่มสมาชิกใหม่ มี 2 แบบ คือ

* **append** : ใส่เป็นคำ หรือตัวเลขก็ได้ => `list.append()`
* **extend**  : ใส่เป็น string character => `list.extend([])`

อื่นๆ

* การลบสมาชิกออก ใช้ `list.remove()` ข้างในใส่สมาชิกตัวที่เราต้องการจะลบ
* ถ้าล้างไส้ในทั้งหมด ใช้ `list.clear()`
* การตรวจสอบความยาวของ list ใช้คำสั่ง `len(list)`

**ตัวอย่างการใช้งาน**

```python
fav_stock = ["ADVANC", "BEM", "CPALL", "CPF", "AU"]
```

1. เพิ่ม "BAY"
2. ลบ "AU"
3. เปลี่ยน "ADVANC" เป็น "INTOUCH"
4. หาจำนวนชื่อหุ้นใน fav_stock

<details>

<summary><strong>คำเฉลย</strong></summary>

```python
fav_stock.append("BAY")
fav_stock.remove("AU")
fav_stock[0] = "INTOUCH"
len(fav_stock)
```

</details>

### Boolean

อันนี้เหมือนภาษาอื่นๆ มีค่าสองแบบเท่านั้น คือ `True` กับ `False`
สรุป python ไม่ต้องประกาศตัวแปรให้วุ่นวาย เช่น `uint8 i = 0;` งี้ แค่ใส่ค่าไปเลย เช่น `i = 0` จบ
