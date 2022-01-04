# Exception handling

### Syntax Error

คือ การที่ compiler แจ้งในส่วนที่เราเขียนโค้ดผิด syntax ที่เราพบเห็นกัน มีดังนี้

* **SyntaxError** : invalid syntax
* **IndexError**: string index out of range
* **NameError**: name 'n' is not defined

### Exception

คือ การที่ compiler แจ้งเราว่า code error ไม่สามารถทำงานต่อได้ มี Error defect ดังนี้

* **ZeroDivisionError**: division by zero
* **NameError**: name 'test2' is not defined
* **TypeError**: unsupported operand type(s) for -: 'str' and 'int'

### Handling Exception

การจัดการเมื่อโค้ดของเรามีปัญหา มี syntax การเขียน ดังนี้

```python
try:
   // Protected code
except:
   // Catch block
else:
   // The finally block always executes.
```

การทำงาน ทำในส่วนของ try ก่อน ถ้าทำงานในส่วนนี้สำเร็จ ก็คือจบ ถ้าไม่สำเร็จ จะไปในส่วนของ except ต่อ

### Raising Exceptions

ถ้าเปรียบเทียบกับ JAVA เหมือน throw

```python
raise ValueError('A very specific bad thing happened')
```

ตัวอย่างการใช้งาน เช่น การหารด้วยศูนย์

```python
try:
   result = input1 / input2
except ZeroDivisionError:
   print (“cannot divide by 0”)
```
