# Workshop: Data Analytics with Excel Pivot Table & Interactive Dashboard

## หลักสูตร

การวิเคราะห์ข้อมูลโครงการสุขภาพด้วย Pivot Table, Pivot Chart, KPI Card และ Interactive Dashboard

## ชุดข้อมูล

ไฟล์

**NHSO_Project_Monitoring_77Province.csv**

- 77 จังหวัด
- 5 ภูมิภาค
- 12 เดือน
- 10 ประเภทโครงการ
- 9,120 รายการข้อมูล

ใช้สำหรับการสร้าง

- Pivot Table
- Pivot Chart
- KPI Card
- Interactive Dashboard
- AI Insight Analysis

---

# Learning Objectives

หลังจบ Workshop ผู้เรียนสามารถ

✅ สร้าง Pivot Table

✅ สร้าง Pivot Chart

✅ สร้าง KPI Card

✅ สร้าง Dashboard

✅ ใช้ Slicer กรองข้อมูล

✅ วิเคราะห์ข้อมูลด้วย AI

✅ สรุป Insight สำหรับผู้บริหาร

---

# Dataset Structure

| Column | Description |
|----------|----------|
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
| Satisfaction | ความพึงพอใจ |

---

# Part 1: Data Preparation

## Step 1 Import CSV

เปิด Excel

เลือก

```text
Data
→ From Text / CSV
```

เลือกไฟล์

```text
NHSO_Project_Monitoring_77Province.csv
```

กด

```text
Load
```

---

## Step 2 Convert to Table

เลือกข้อมูลทั้งหมด

```text
Ctrl + T
```

ติ๊ก

```text
My table has headers
```

---

## Step 3 Rename Table

เปลี่ยนชื่อ

```text
tbl_Project
```

---

# Part 2: Create First Pivot Table

## Budget by Region

เลือก

```text
Insert
→ Pivot Table
```

---

เลือก

```text
New Worksheet
```

---

เปลี่ยนชื่อ Sheet

```text
Pivot_Budget
```

---

## Configure Fields

Rows

```text
Region
```

---

Values

```text
Budget
```

---

ผลลัพธ์

| Region | Budget |
|----------|----------|
| North | xxx |
| Central | xxx |
| Northeast | xxx |
| East | xxx |
| South | xxx |

---

# Workshop 1

## วิเคราะห์งบประมาณรายภูมิภาค

ตอบคำถาม

- ภูมิภาคใดได้รับงบประมาณมากที่สุด
- ภูมิภาคใดได้รับงบประมาณน้อยที่สุด

---

# Part 3: Create KPI Pivot Table

สร้าง Sheet

```text
Pivot_KPI
```

---

Rows

ไม่ต้องใส่

---

Values

```text
Sum of Budget
```

```text
Sum of Actual_Spend
```

```text
Count of Project_ID
```

```text
Average of KPI_Actual
```

---

ผลลัพธ์

```text
Budget
Actual Spend
Projects
Average KPI
```

---

# Workshop 2

## วิเคราะห์ตัวชี้วัดภาพรวม

ตอบคำถาม

- งบประมาณรวมเท่าไร
- เบิกจ่ายเท่าไร
- จำนวนโครงการทั้งหมด
- KPI เฉลี่ยระดับประเทศ

---

# Part 4: Create KPI Cards

สร้าง Sheet

```text
Dashboard
```

---

## Card 1: Budget

เซลล์

```excel
B3
```

สูตร

```excel
='Pivot_KPI'!B4
```

---

หัวข้อ

```text
B2 = Total Budget
```

---

## Card 2: Budget Utilization

เซลล์

```excel
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

## Card 3: Projects

เซลล์

```excel
H3
```

สูตร

```excel
='Pivot_KPI'!B6
```

---

## Card 4: KPI Achievement

เซลล์

```excel
K3
```

สูตร

```excel
='Pivot_KPI'!B7
```

---

Format

```text
Percentage
```

---

# Formatting KPI Cards

เลือกช่วง

```text
B2:C4
```

ใส่

```text
Fill Color : Dark Blue

Font Color : White

Font Size : 24
```

---

ทำซ้ำกับ

```text
E2:F4

H2:I4

K2:L4
```

---

# Part 5: Create Pivot Chart

## Chart 1: Budget by Region

เลือก Pivot Table

```text
Pivot_Budget
```

---

เลือก

```text
Insert
→ Column Chart
```

---

ชื่อกราฟ

```text
Budget by Region
```

---

# Chart 2: KPI by Region

สร้าง Pivot ใหม่

Rows

```text
Region
```

---

Values

```text
Average KPI_Actual
```

---

สร้าง

```text
Clustered Column Chart
```

---

ชื่อกราฟ

```text
KPI Performance by Region
```

---

# Chart 3: KPI Target vs Actual

สร้าง Pivot ใหม่

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

กำหนดสี

```text
Target = Gray

Actual = Green
```

---

# Chart 4: Monthly Trend

สร้าง Pivot ใหม่

Rows

```text
Month
```

---

Values

```text
Sum Budget
```

---

สร้าง

```text
Line Chart
```

---

ชื่อกราฟ

```text
Monthly Budget Trend
```

---

# Part 6: Create Interactive Dashboard

## Insert Slicer

คลิก Pivot Table

---

เลือก

```text
PivotTable Analyze
→ Insert Slicer
```

---

เลือก

```text
Region

Province

Month

Project_Name
```

---

กด

```text
OK
```

---

# Connect Slicer

คลิก

```text
Slicer
```

---

เลือก

```text
Report Connections
```

---

เลือก Pivot ทุกตัว

```text
Pivot_KPI

Pivot_Budget

Pivot_KPI_Region

Pivot_Target_Actual

Pivot_Monthly
```

---

# Test Dashboard

เลือก

```text
Month = Jan
```

ตรวจสอบ

✅ KPI Cards เปลี่ยน

✅ Charts เปลี่ยน

---

เลือก

```text
Province = Chiang Mai
```

Dashboard เปลี่ยนทั้งหมด

---

# Dashboard Layout

```text
+--------------------------------------------------------+

 KPI Cards

 Budget
 Utilization
 Projects
 KPI Achievement

+--------------------+--------------------+

 Budget by Region

 KPI by Region

+--------------------+--------------------+

 KPI Target vs Actual

 Monthly Trend

+--------------------------------------------------------+

 Province Ranking

+--------------------------------------------------------+

 Region Slicer

 Province Slicer

 Month Slicer

 Project Slicer

+--------------------------------------------------------+
```

---

# Part 7: AI Insight Analysis

## Prompt 1

```text
คุณเป็นนักวิเคราะห์ข้อมูลด้านสุขภาพ

วิเคราะห์ Dashboard นี้

1. สรุป Insight สำคัญ 5 ข้อ
2. จังหวัดที่มี KPI สูงที่สุด
3. จังหวัดที่มี KPI ต่ำที่สุด
4. จังหวัดที่ใช้งบประมาณสูงสุด
5. แนวโน้มการเบิกจ่ายงบประมาณ
```

---

## Prompt 2

```text
วิเคราะห์ KPI Dashboard

1. พื้นที่ที่ควรติดตาม
2. พื้นที่ต้นแบบ
3. ความเสี่ยงที่พบ
4. ข้อเสนอแนะเชิงนโยบาย
```

---

## Prompt 3

```text
สรุปผล Dashboard นี้

สำหรับผู้บริหาร

ไม่เกิน 1 หน้า
```

---

# Workshop Challenge

## Task 1

สร้าง Pivot Table

```text
Budget by Region
```

---

## Task 2

สร้างกราฟ

```text
KPI Target vs Actual
```

---

## Task 3

สร้าง KPI Cards

```text
Budget

Budget Utilization

Projects

KPI Achievement
```

---

## Task 4

เพิ่ม Slicer

```text
Region

Province

Month

Project
```

---

## Task 5

ใช้ AI วิเคราะห์ Dashboard

สรุป

```text
5 Key Insights
```

---

# Expected Output

✅ Pivot Table

✅ Pivot Chart

✅ KPI Card

✅ Interactive Dashboard

✅ Slicer

✅ Executive Dashboard

✅ AI Insight

✅ พร้อมต่อยอดสู่ Power BI
