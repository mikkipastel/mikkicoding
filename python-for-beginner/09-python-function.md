# Function

มี syntax การเขียนดังนี้

```python
def fn_name(input):
   …

   return output
```

เรามีวิธีง่ายๆ นั่นคือ การนำโปรแกรมตัดเกรดของเรามาใส่ในฟังก์ชั่น โดยมี input คือ คะแนนของนักเรียนในวิชาการเรียน python พื้นฐาน และ คืนค่าเป็นเกรดของนักเรียน

```python
def python_grade(score)
  # ใส่โปรแกรมตัดเกรดของเราลงไป
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
  return grade
```

การเรียกใช้งาน เป็นดังนี้ `python_grade(78)`

ถ้าต้องการแสดงผล สามารถใส่ print ครอบไว้ได้ `print(python_grade(78))`
