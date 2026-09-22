# 📊 Workshop 1: การสร้าง Pivot Table และ Dashboard ด้วย Excel

## วัตถุประสงค์
- จัดเตรียมข้อมูลสำหรับการวิเคราะห์
- สร้าง Excel Table
- สร้าง Pivot Table
- สร้าง Pivot Chart
- สร้าง Dashboard สำหรับผู้บริหาร
- ใช้ Slicer เพื่อกรองข้อมูลแบบ Interactive
- วิเคราะห์ Insight จาก Dashboard ร่วมกับ AI

---

# ชุดข้อมูลที่ใช้

ไฟล์

**NHSO_Project_Monitoring.csv**

## รายละเอียดข้อมูล

| Field | Description |
|---------|---------|
| Project_ID | รหัสโครงการ |
| Project_Name | ชื่อโครงการ |
| Region | ภูมิภาค |
| Province | จังหวัด |
| Month | เดือน |
| Budget | งบประมาณ |
| Actual_Spend | ผลการเบิกจ่าย |
| KPI_Target | ค่าเป้าหมาย |
| KPI_Actual | ผลการดำเนินงาน |
| Participants | จำนวนผู้เข้าร่วม |
| Satisfaction | คะแนนความพึงพอใจ |

---

# ส่วนที่ 1 : เตรียมข้อมูล
โหลดข้อมูล 2 ไฟล์ 
1) Thailand_77_Provinces.csv
2) NHSO_Project_Monitoring.csv

## Step 1 เปิดไฟล์ข้อมูล

1. เปิด Microsoft Excel
2. เลือกเมนู
   Data → From Text/CSV
3. เลือกไฟล์
   NHSO_Project_Monitoring.csv
4. กด Load
5. เลือกเมนู
   Home → New Query → New Source → File →Text/Csv 
6. เลือกไฟล์
   Thailand_77_Provinces.csv
7. กด OK

---

## Step 2 ตรวจสอบคุณภาพข้อมูล
ตรวจสอบว่า
✅ ไม่มีแถวว่าง
✅ ไม่มีคอลัมน์ว่าง
✅ Header อยู่แถวแรก
✅ ข้อมูล Budget และ Actual_Spend เป็นตัวเลข
✅ Satisfaction เป็นตัวเลขทศนิยม

---

## Step 3 แปลงข้อมูลเป็น Table

1. คลิกภายในชุดข้อมูล
2. กด
```text
Ctrl + T
```
3. เลือก
```text
My Table Has Headers
```
4. กด OK
5. เปลี่ยนชื่อ Table เป็น
```text
tbl_Project
```
---

# ส่วนที่ 2 : สร้าง Pivot Table
## Workshop 1 : วิเคราะห์งบประมาณตามจังหวัด
### Step 1
เลือกข้อมูลใน Table
---
### Step 2
เลือก
```text
Insert
→ Pivot Table
```
---

### Step 3
เลือก

```text
New Worksheet
```
---
### Step 4
กำหนดฟิลด์
Rows
```text
Province
```
Values

```text
Budget
```
---
### ผลลัพธ์
Pivot Table จะแสดงงบประมาณรวมแยกตามจังหวัด

---

### คำถามวิเคราะห์

- จังหวัดใดได้รับงบประมาณสูงสุด
- จังหวัดใดได้รับงบประมาณต่ำสุด

---

# Workshop 2 : วิเคราะห์ KPI ตามภูมิภาค

## สร้าง Pivot Table ใหม่

Rows

```text
Region
```

Values

```text
Average KPI_Actual
```

---

## ปรับค่า Value Field

เลือก

```text
Value Field Settings
```

เปลี่ยนจาก

```text
Sum
```

เป็น

```text
Average
```

---

## คำถามวิเคราะห์

- ภูมิภาคใดมี KPI สูงที่สุด
- ภูมิภาคใดมี KPI ต่ำกว่าเป้าหมาย

---

# Workshop 3 : วิเคราะห์การเบิกจ่าย

## สร้าง Pivot Table

Rows

```text
Region
```

Values

```text
Budget
Actual_Spend
```

---

## สร้างคอลัมน์คำนวณ

สูตร

```excel
=Actual_Spend/Budget
```

---

## คำถามวิเคราะห์

- ภูมิภาคใดมีอัตราเบิกจ่ายสูงสุด
- ภูมิภาคใดต้องเร่งรัดการเบิกจ่าย

---

# ส่วนที่ 3 : วิเคราะห์แนวโน้มรายเดือน

## Workshop 4 : Monthly Trend

สร้าง Pivot Table

Rows

```text
Month
```

Columns

```text
Region
```

Values

```text
Sum Budget
```

---

## คำถามวิเคราะห์

- ช่วงเดือนใดใช้งบประมาณสูงที่สุด
- ภูมิภาคใดมีแนวโน้มเพิ่มขึ้น

---

# ส่วนที่ 4 : สร้าง Pivot Chart

## Workshop 5 : Budget by Region

เลือก Pivot Table

จากนั้น

```text
Insert
→ Column Chart
```

---

## ปรับแต่งกราฟ

Chart Title

```text
Budget by Region
```

---

## หลักการเลือกกราฟ

### Column Chart

เหมาะสำหรับ

```text
การเปรียบเทียบ
```

---

### Line Chart

เหมาะสำหรับ

```text
แนวโน้มตามเวลา
```

---

### Doughnut Chart

เหมาะสำหรับ

```text
สัดส่วน
```

---

# Workshop 6 : KPI by Region

สร้าง Pivot Chart

ข้อมูล

```text
Average KPI_Actual
```

---

## ตั้งชื่อกราฟ

```text
KPI Performance by Region
```

---

# ส่วนที่ 5 : สร้าง Dashboard

## ออกแบบ Dashboard

### Dashboard Sheet

สร้าง Sheet ใหม่ชื่อ

```text
Dashboard
```

---

## KPI Card 1

### Total Budget

สูตร

```excel
=SUM(tbl_Project[Budget])
```

---

## KPI Card 2

### Budget Utilization

สูตร

```excel
=SUM(tbl_Project[Actual_Spend])/SUM(tbl_Project[Budget])
```

---

## KPI Card 3

### Number of Projects

สูตร

```excel
=COUNTA(tbl_Project[Project_ID])
```

---

## KPI Card 4

### Average KPI

สูตร

```excel
=AVERAGE(tbl_Project[KPI_Actual])
```

---

# Dashboard Layout

```text
+------------------------------------------------------+
| KPI CARDS                                             |
+------------------------------------------------------+

Budget
Utilization
Projects
KPI

+----------------------+----------------------+
| Budget by Region     | KPI by Region        |
+----------------------+----------------------+

+---------------------------------------------+
| Monthly Trend                               |
+---------------------------------------------+

+---------------------------------------------+
| Top 10 Provinces                            |
+---------------------------------------------+
```

---

# ส่วนที่ 6 : Slicer

## Workshop 7 : Interactive Dashboard

### เพิ่ม Slicer

เลือก Pivot Table

จากนั้น

```text
PivotTable Analyze
→ Insert Slicer
```

---

### เลือกฟิลด์

```text
Region
Province
Month
```

---

## การเชื่อม Slicer ทุก Pivot

เลือก Slicer

```text
Report Connections
```

หรือ

```text
PivotTable Connections
```

เลือก Pivot ทุกตัว

---

# ส่วนที่ 7 : Top 10 จังหวัด

## สร้าง Pivot Table

Rows

```text
Province
```

Values

```text
Average KPI_Actual
```

---

## Sort

```text
Largest to Smallest
```

---

## Filter

```text
Top 10
```

---

## สร้างกราฟ

```text
Top 10 KPI Provinces
```

---

# ส่วนที่ 8 : วิเคราะห์ข้อมูลด้วย AI

## Prompt วิเคราะห์ Dashboard

```text
คุณเป็นนักวิเคราะห์นโยบายสุขภาพ

จาก Dashboard นี้

1. สรุป Insight สำคัญ 5 ข้อ
2. จังหวัดที่มีความเสี่ยง
3. ภูมิภาคที่มี KPI ต่ำกว่าเป้าหมาย
4. แนวโน้มการเบิกจ่ายงบประมาณ
5. ข้อเสนอแนะสำหรับผู้บริหาร
```

---

# แบบฝึกหัดท้าย Workshop

## Task 1

สร้าง Pivot Table

แสดง

```text
Budget by Province
```

---

## Task 2

สร้าง Pivot Table

แสดง

```text
Average KPI by Region
```

---

## Task 3

สร้าง Pivot Chart

แสดง

```text
Monthly Budget Trend
```

---

## Task 4

สร้าง Dashboard

ประกอบด้วย

- KPI Cards
- Budget by Region
- KPI by Region
- Monthly Trend
- Top 10 Provinces

---

## Task 5

เพิ่ม Slicer

- Region
- Province
- Month

---

# ผลลัพธ์ที่คาดหวัง

ผู้เรียนสามารถ

✅ สร้าง Excel Table

✅ สร้าง Pivot Table

✅ สร้าง Pivot Chart

✅ ใช้ Slicer

✅ สร้าง Dashboard ผู้บริหาร

✅ วิเคราะห์ Insight ด้วย AI

✅ นำข้อมูลไปต่อยอดใน Power BI ได้
