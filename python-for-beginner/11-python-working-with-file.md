# การทำงานร่วมกันกับไฟล์

การอ่านไฟล์ มี syntax หลักๆ ดังนี้

```python
f = open(filename, mode)
```

parameter ตัวแรก คือ ชื่อไฟล์ และตัวที่สอง คือโหมดการอ่านเขียนไฟล์

**โหมดการเขียนอ่านไฟล์** มีดังนี้

* r : read อ่าน
* w : overwrite เขียนทับ
* a : write at end of the file เขียนต่อ
* mode++ : reading & writing => r+, w+ a+

มาดูการเขียนโค้ดกันดีกว่า

```python
# open file
f = open(‘text.txt’, ‘a’)

# read file 
code = f.read()
```

หลังจากอ่านไฟล์แล้ว สามารถส่วนนี้ไปใช้งานได้ แต่ประเภทของตัวแปรจะเป็นแบบ binary ดังนั้นอาจจะต้องแปลงเป็น string โดยใช้ `decode("utf-8")` เช่น

```python
# find word in line of file
if (code.find(b"file") >= 0):
  print (code)

elif (code.decode("utf-8").find(b"line") >= 0):
  print (code)

# spilt line
lines = code.strip().splitlines()

# read single line of a file
f.readline()

# write file
f.write(“blah blah blah”)

#close file
f.close()
```
