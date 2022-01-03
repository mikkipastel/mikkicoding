# การใช้ break, continue และ pass ใน statement

**`break`** คือ การให้โค้ดของเราหยุดทำงาน เมื่อเข้าสู่ statement ที่เรากำหนด

**`continue`** คือหลังจากเจอ statement ที่เรากำหนด ก็ให้ตรวจที่ statement ถัดไป

**`pass`** ใส่เมื่อเราไม่ให้มีการทำงานใดๆเมื่อเข้า statement ที่เรากำหนด

ตัวอย่าง

```
# check order
if (order == 0):
  break
elsif (order == 1):
  continue
elif (order % 3 == 0):
  pass
else:
  print (order)
```
