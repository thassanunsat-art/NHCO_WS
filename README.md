# Workshop: การวิเคราะห์ข้อมูลด้วย Pivot Table และสร้าง Interactive Dashboard ด้วย Excel
## ชุดข้อมูลที่ใช้
ไฟล์
NHSO_Project_Monitoring.csv
---
# วัตถุประสงค์
✅ สร้าง Pivot Table

✅ สร้าง Pivot Chart
✅ สร้าง KPI Card
✅ สร้าง Interactive Dashboard
✅ ใช้ Slicer และ Timeline
✅ ใช้ AI วิเคราะห์ Key Insight
---

# โครงสร้างข้อมูล

| Field | Description |
|---------|---------|
| Project_ID | รหัสโครงการ |
| Project_Name | ชื่อโครงการ |
| Region | ภูมิภาค |
| Province | จังหวัด |
| Month | เดือน |
| Budget | งบประมาณ |
| Actual_Spend | ผลการเบิกจ่าย |
| KPI_Target | เป้าหมาย |
| KPI_Actual | ผลการดำเนินงาน |
| Participants | จำนวนผู้เข้าร่วม |
| Satisfaction | ความพึงพอใจ |

---

# Part 1 : เตรียมข้อมูล
## Step 1 เปิดไฟล์
เปิดไฟล์
NHSO_Project_Monitoring.csv

---

## Step 2 แปลงเป็น Excel Table
เลือกข้อมูลทั้งหมด

```text
Ctrl + T
```

เลือก

```text
My table has headers
```

---

## Step 3 ตั้งชื่อ Table

```text
tbl_Project
```

---

# Part 2 : การสร้าง Calculated Field ใน Pivot Table
## วัตถุประสงค์
เรียนรู้การสร้างค่าคำนวณใหม่ภายใน Pivot Table โดยไม่ต้องแก้ไขข้อมูลต้นทาง

ข้อดี
✅ ไม่ต้องเพิ่มคอลัมน์ใน Source Data
✅ คำนวณได้ทันที
✅ เปลี่ยนตาม Slicer อัตโนมัติ
✅ เหมาะสำหรับ Dashboard
---

# Calculated Field คืออะไร
Calculated Field คือ

การสร้างสูตรคำนวณใหม่จากฟิลด์ที่มีอยู่ใน Pivot Table

ตัวอย่าง
```text
Budget Utilization
= Actual Spend ÷ Budget
```

หรือ

```text
Budget Remaining
= Budget - Actual Spend
```

---
# Workshop 1 : สร้าง Budget Utilization

## ขั้นตอนที่ 1
คลิกภายใน Pivot Table
---

## ขั้นตอนที่ 2
เลือก
```text
PivotTable Analyze
→ Fields, Items & Sets
→ Calculated Field
```

---
## ขั้นตอนที่ 3
กำหนด
Name
```text
Budget Utilization
```
Formula
```text
=Actual_Spend/Budget
```
---
## ขั้นตอนที่ 4
กด
```text
Add
```
แล้ว
```text
OK
```
---

# ผลลัพธ์
Pivot Table จะมี Field ใหม่

```text
Budget Utilization
```

---

## เปลี่ยนรูปแบบ

คลิก

```text
Value Field Settings
→ Number Format
→ Percentage
```

---

# Workshop 2 : สร้าง Budget Remaining

## สูตร

```text
=Budget-Actual_Spend
```

---

## Name

```text
Budget Remaining
```

---

# ผลลัพธ์

แสดงงบประมาณคงเหลือ

```text
Budget - Actual Spend
```

ของแต่ละพื้นที่

---

# Workshop 3 : สร้าง KPI Gap

## แนวคิด

หาค่าที่ต่ำกว่าเป้าหมาย

---

## สูตร

```text
=KPI_Target-KPI_Actual
```

---

## Name

```text
KPI Gap
```

---

# ผลลัพธ์

| Region | KPI Gap |
|----------|----------|
| North | 11 |
| Central | 14 |
| Northeast | 22 |
| South | 9 |

---

# Workshop 4 : วิเคราะห์ Budget Utilization

## Pivot Table

Rows

```text
Region
```

Values

```text
Budget Utilization
```

---

## คำถาม

- ภูมิภาคใดเบิกจ่ายดีที่สุด
- ภูมิภาคใดเบิกจ่ายต่ำสุด
- พื้นที่ใดควรเร่งรัดงบประมาณ

---

# Workshop 5 : วิเคราะห์ KPI Gap

## Pivot Table

Rows

```text
Region
```

Values

```text
KPI Gap
```

---

## คำถาม

- ภูมิภาคใดห่างจากเป้าหมายมากที่สุด
- พื้นที่ใดใกล้บรรลุเป้าหมาย

---

# ข้อจำกัดของ Calculated Field

Calculated Field

✅ บวก

✅ ลบ

✅ คูณ

✅ หาร

✅ สูตรพื้นฐาน

---

Calculated Field

❌ ไม่รองรับ IF

❌ ไม่รองรับ XLOOKUP

❌ ไม่รองรับ SUMIFS

❌ ไม่รองรับฟังก์ชันซับซ้อน

---

# เมื่อใดควรใช้ Calculated Column

ถ้าต้องการ

```text
Project Status

Passed
Need Improvement
```

เช่น

```excel
IF(KPI_Actual>=80,"Passed","Need Improvement")
```

ควรสร้างใน Source Data

ก่อนทำ Pivot

---

# Best Practice

ใช้ Pivot Calculated Field สำหรับ

✅ Budget Utilization

✅ Budget Remaining

✅ KPI Gap

---

ใช้ Source Data Column สำหรับ

✅ Status

✅ Category

✅ Group

✅ Classification

---

# ผลลัพธ์ที่คาดหวัง

ผู้เรียนสามารถ

✅ สร้าง Calculated Field

✅ วิเคราะห์ KPI

✅ วิเคราะห์การเบิกจ่าย

✅ สร้าง Pivot Chart จากฟิลด์คำนวณ

✅ ใช้งานร่วมกับ Slicer และ Dashboard ได้

# Part 3 : สร้าง Pivot Table

## Pivot Table 1 : Budget by Region

เลือก

```text
Insert
→ Pivot Table
```

วางที่

```text
Dashboard!A15
```

---

### Rows

```text
Region
```

### Values

```text
Sum of Budget
```

---

## Pivot Table 2 : KPI by Region

Rows

```text
Region
```

Values

```text
Average KPI_Actual
```

---

## Pivot Table 3 : KPI Achievement

Rows

```text
Region
```

Values

```text
Average KPI_Achievement
```

---

## Pivot Table 4 : Monthly Trend

Rows

```text
Month
```

Values

```text
Sum Budget
```

---

## Pivot Table 5 : Top 10 Province

Rows

```text
Province
```

Values

```text
Average KPI_Actual
```

Sort

```text
Largest to Smallest
```

Filter

```text
Top 10
```

---

# Part 4 : สร้าง Pivot Chart

## Chart 1 : Budget by Region

เลือก Pivot Table

```text
Budget by Region
```

---

สร้าง

```text
Insert
→ Column Chart
```

---

เปลี่ยนชื่อ

```text
Budget by Region
```

---

# Chart 2 : KPI Performance by Region

เลือก Pivot

```text
KPI by Region
```

---

สร้าง

```text
Clustered Column Chart
```

---

เปลี่ยนชื่อ

```text
KPI Performance by Region
```

---

# Chart 3 : KPI Target vs Actual

## สร้าง Pivot

Rows

```text
Region
```

---

Values

```text
Average KPI_Target
Average KPI_Actual
```

---

สร้าง

```text
Clustered Column Chart
```

---

เปลี่ยนสี

```text
Target = Gray
Actual = Green
```

---

# Chart 4 : Monthly Budget Trend

เลือก Pivot

```text
Month
```

---

สร้าง

```text
Line Chart
```

---

เปลี่ยนชื่อ

```text
Monthly Budget Trend
```

---

# Part 5 : สร้าง KPI Cards

## KPI Card 1

งบประมาณรวม

สร้าง Pivot KPI

ลาก

```text
Budget
```

ลง Values

---

ที่เซลล์

```text
B3
```

ใส่สูตร

```excel
='Pivot_KPI'!B4
```

---

## KPI Card 2

อัตราการเบิกจ่าย

ที่

```text
E3
```

สูตร

```excel
='Pivot_KPI'!B5/'Pivot_KPI'!B4
```

---

Format

```text
Percentage
```

---

## KPI Card 3

จำนวนโครงการ

ที่

```text
H3
```

สูตร

```excel
='Pivot_KPI'!B6
```

---

## KPI Card 4

KPI Achievement

ที่

```text
