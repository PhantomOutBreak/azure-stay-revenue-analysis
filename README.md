# 🏨 Azure Stay Revenue Analysis  
## การวิเคราะห์ปัจจัยที่ส่งผลต่อรายได้ของโรงแรมและประสิทธิภาพการตั้งราคา

โครงการนี้จัดทำขึ้นเพื่อวิเคราะห์ปัญหา **Revenue Stagnation** ของโรงแรมสมมติ **Azure Stay** ซึ่งแม้จะมีจำนวนการจองในระดับที่ดี แต่รายได้ต่อห้องพักยังไม่เติบโตตามศักยภาพที่ควรจะเป็น

การวิเคราะห์นี้มุ่งเน้นการใช้แนวคิดด้าน **Business Intelligence, Data Analytics และ Exploratory Data Analysis (EDA)** เพื่อศึกษา:
- ผลกระทบของช่องทางการจอง (Booking Channel)
- ผลของกลยุทธ์ด้านราคา (Rate Code / Promotion)
- ความแตกต่างระหว่างช่วงเวลา (Weekend vs Weekday)
- คุณค่าทางธุรกิจของลูกค้าแต่ละกลุ่ม (Customer Segment)

โดยมีเป้าหมายเพื่อค้นหา insight ที่สามารถนำไปใช้ในการปรับกลยุทธ์ด้านราคาและการบริหารรายได้ของโรงแรมได้จริง

---

# 📌 1. Background & Pain Points

Azure Stay กำลังเผชิญปัญหา **Revenue Stagnation (รายได้หยุดนิ่ง)**  
แม้มีจำนวนผู้เข้าพักในระดับที่ดี แต่ค่า **RevPAR (Revenue Per Available Room)** ไม่เติบโต และไม่สอดคล้องกับต้นทุนการดำเนินงานที่เพิ่มขึ้น

สถานการณ์นี้สะท้อนถึงความไม่มีประสิทธิภาพในการบริหารรายได้ของโรงแรม โดยเฉพาะในด้าน **Pricing Strategy** และ **Inventory Management**

## ⚠️ Pain Points
- **Inefficient Pricing**  
  การตั้งราคาห้องพักไม่สอดคล้องกับระดับความต้องการ (Demand) ทำให้พลาดโอกาสในการเพิ่มรายได้

- **Poor Inventory Management**  
  การจัดการ Length of Stay (LOS) และ Booking Lead Time (BLT) ยังไม่เหมาะสม ทำให้ใช้ทรัพยากรห้องพักได้ไม่เต็มประสิทธิภาพ

- **Impact on Profitability**  
  RevPAR ที่ไม่เติบโตส่งผลต่อกำไร ความสามารถในการแข่งขัน และโอกาสในการสร้างรายได้ระยะยาว

> 💡 สรุป: ปัญหาไม่ได้อยู่ที่ จำนวน booking เพียงอย่างเดียว แต่เกี่ยวข้องกับคุณภาพของรายได้ ช่องทางการจอง และกลยุทธ์ด้านราคา

---

# 🎯 2. Objectives

โครงการนี้มีวัตถุประสงค์เพื่อ:

- วิเคราะห์ปัจจัยที่ทำให้รายได้ของโรงแรมไม่เติบโต
- ประเมินผลของ **Booking Channel**, **Rate Code**, **Day Type**, และ **Customer Segment** ต่อรายได้
- ศึกษา trade-off ระหว่าง **Demand (จำนวนการจอง)** และ **Revenue per Booking**
- ระบุโอกาสในการเพิ่มรายได้ผ่านการปรับ **Pricing Strategy**
- จัดทำ insight เพื่อสนับสนุนการตัดสินใจด้าน **Revenue Management**

---

# ❓ 3. Business Questions

คำถามทางธุรกิจหลักของโครงการนี้ ได้แก่:

1. ช่องทางการจองใดสร้างรายได้เฉลี่ยต่อ booking สูงที่สุด
2. โปรโมชั่นและส่วนลดส่งผลต่อจำนวนการจองและรายได้ต่อ booking อย่างไร
3. Weekend และ Weekday มีรูปแบบ demand และรายได้แตกต่างกันหรือไม่
4. Customer Segment ใดเป็นกลุ่ม High Volume และกลุ่มใดเป็น High Value
5. โรงแรมควรปรับกลยุทธ์ด้านราคาอย่างไรเพื่อเพิ่มรายได้โดยรวม

---

# 🧪 4. Hypotheses

## H1: Channel Effect
คาดว่าช่องทาง **Direct** และ **Corporate** จะมีรายได้เฉลี่ยต่อ booking สูงกว่าช่องทาง **OTA** เนื่องจาก OTA มีต้นทุนค่าคอมมิชชั่น

## H2: Pricing Effect
คาดว่า Rate Code ที่เป็นโปรโมชั่นหรือส่วนลดจะช่วยเพิ่มจำนวนการจอง (Demand) แต่ทำให้รายได้เฉลี่ยต่อ booking ลดลง

## H3: Demand Timing Effect
คาดว่า Weekday และ Weekend จะมีรูปแบบ demand และรายได้ต่างกัน โดยแต่ละช่วงเวลาควรใช้กลยุทธ์ pricing ที่แตกต่างกัน

---

# 🗂️ 5. Dataset Description

ชุดข้อมูลที่ใช้ในโครงการนี้เป็นข้อมูลการจองของโรงแรมที่สร้างขึ้นในรูปแบบ CSV เพื่อจำลองโครงสร้างข้อมูลจริงของธุรกิจโรงแรม

---

- จำนวนแถวข้อมูล: 9,515 แถว
- จำนวนตัวแปร: 25 คอลัมน์

---

## ไฟล์ข้อมูลหลัก
- `fact_bookings_clean.csv` : ตารางข้อมูลการจองหลัก
- `fact_bookings_enriched.csv` : ตารางข้อมูลที่ผ่านการรวมและเตรียมสำหรับการวิเคราะห์
- `dim_channels.csv` : ข้อมูลช่องทางการจอง
- `dim_rate_codes.csv` : ข้อมูลประเภทของราคา / โปรโมชั่น
- `dim_segments_clean.csv` : ข้อมูลกลุ่มลูกค้า
- `dim_calendar.csv` : ข้อมูลด้านวันและช่วงเวลา
- `dim_room_inventory.csv` : ข้อมูล capacity / inventory ของโรงแรม

## คอลัมน์สำคัญที่ใช้
- `channel_id`
- `rate_code_id`
- `segment_id`
- `day_type`
- `booking_id`
- `True_Room_Revenue`
- `Penalty_Revenue`
- `commission_amount`
- `net_realized_revenue`

---

# 🧹 6. Data Cleaning & Preparation

ก่อนทำการวิเคราะห์ ได้มีการเตรียมและตรวจสอบข้อมูลดังนี้:

- ตรวจสอบ Missing Values
- ตรวจสอบความซ้ำซ้อนของ `booking_id`
- ตรวจสอบความถูกต้องของรายได้
- แยกรายได้ออกเป็น:
  - **True Room Revenue** = รายได้จากการเข้าพักจริง
  - **Penalty Revenue** = รายได้จากค่าปรับกรณี cancel / no-show
- เพิ่มคอลัมน์ `day_type` เพื่อแบ่งข้อมูลเป็น **Weekend** และ **Weekday**
- ตรวจสอบ consistency ของ commission และ net revenue

> หมายเหตุ: ชุดข้อมูลนี้ถูกออกแบบให้สะท้อน business logic ของโรงแรม เช่น OTA commission, promotional pricing และ customer segment behavior

---

# 📊 Exploratory Data Analysis (EDA)

## 1) Booking Channel Analysis

Direct และ Corporate มีรายได้เฉลี่ยต่อ booking สูงกว่า OTA  
สะท้อนถึงผลกระทบของค่าคอมมิชชั่นต่อรายได้สุทธิ

![Average Revenue by Booking Channel](images/h1_channel_average_revenue.png)

---

## 2) Pricing Analysis

Promotion ช่วยเพิ่มจำนวนการจอง แต่ลดรายได้เฉลี่ยต่อ booking  
แสดงถึง trade-off ระหว่าง **Demand** และ **Revenue**

### Average Revenue by Rate Code
![Average Revenue by Rate Code](images/h2_ratecode_average_revenue.png)

### Number of Bookings by Rate Code
![Number of Bookings by Rate Code](images/number_of_bookings_by_rate_code.png)

---

## 3) Time Analysis (Weekend vs Weekday)

Weekday มีจำนวนการจองสูงกว่า  
ขณะที่ Weekend มีรายได้เฉลี่ยต่อ booking สูงกว่า

### Number of Bookings by Day Type
![Number of Bookings by Day Type](images/h3_daytype_bookings.png)

### Average Revenue by Day Type
![Average Revenue by Day Type](images/h3_daytype_revenue.png)

---

## 4) Customer Segment Analysis

SEG_LEI เป็นกลุ่ม **High Volume**  
ขณะที่ SEG_TRA เป็นกลุ่ม **High Value**

### Average Revenue per Booking by Customer Segment
![Average Revenue per Booking by Customer Segment](images/customer_segment_revenue_per_booking.png)

### Number of Bookings by Customer Segment
![Number of Bookings by Customer Segment](images/customer_segment_number_of_bookings.png)

---

## 📊 Additional Analysis

### Revenue Distribution

![Revenue Distribution](images/true_room_revenue_distribution.png)

การกระจายของ True Room Revenue มีลักษณะ **เบ้ขวา (Right-skewed)**  
โดยรายได้ส่วนใหญ่กระจุกตัวอยู่ในช่วงระดับกลาง (ประมาณ 2,000 – 6,000 THB)  

อย่างไรก็ตาม มี booking บางส่วนที่มีมูลค่าสูงมาก ซึ่งทำให้ค่าเฉลี่ย (Mean) สูงขึ้น  
สะท้อนถึงการมี **High-value booking** เช่น ลูกค้ากลุ่มพรีเมียมหรือ group booking

---

### Outlier Detection (Revenue)

![Outlier Detection](images/eda_outlier_revenue.png)

จาก Boxplot พบว่า:

- มี **outliers จำนวนมาก** ในช่วงรายได้สูง (มากกว่า ~10,000 THB)
- ค่าเฉลี่ย (Mean) สูงกว่าค่ามัธยฐาน (Median) อย่างชัดเจน  
  → ยืนยันว่าข้อมูลมีการกระจายแบบ skewed

📌 Insight:
- รายได้ของโรงแรมไม่ได้มาจาก booking ทั่วไปเท่านั้น  
- แต่มี booking มูลค่าสูงที่ช่วย **boost revenue อย่างมีนัยสำคัญ**

📌 Implication:
- ควรแยกวิเคราะห์กลุ่มลูกค้า High-value ออกมาเฉพาะ  
- เพื่อนำไปออกแบบ **pricing strategy / premium offering** ได้ดียิ่งขึ้น

---

# 📌 Key Findings

- Direct และ Corporate มีประสิทธิภาพด้านรายได้สูงกว่า OTA
- Promotion ช่วยเพิ่ม demand แต่ลดรายได้ต่อ booking
- Weekday ขับเคลื่อนรายได้ด้วย **volume** ขณะที่ Weekend ขับเคลื่อนด้วย **value**
- Customer Segment มีความแตกต่างระหว่าง High Volume และ High Value อย่างชัดเจน

---

# 💡 9. Strategic Recommendations

จากผลการวิเคราะห์ มีข้อเสนอแนะดังนี้:

- เพิ่มสัดส่วน **Direct Booking** เพื่อลดต้นทุนค่าคอมมิชชั่นจาก OTA
- ใช้ **Dynamic Pricing** ให้เหมาะสมกับช่วงเวลา โดยเฉพาะ Weekend
- ใช้โปรโมชั่นอย่างระมัดระวัง เพื่อไม่ให้กระทบรายได้ต่อ booking มากเกินไป
- เพิ่ม focus ไปยังลูกค้ากลุ่ม **High Value Segment**
- ใช้ข้อมูล demand และ booking pattern เพื่อสนับสนุนการตัดสินใจด้าน Revenue Management

---

# 📈 10. Dashboard

โครงการนี้มีการจัดทำ Dashboard ใน Tableau เพื่อสรุปผลการวิเคราะห์ในมิติต่าง ๆ ได้แก่:

- Booking Channel
- Rate Code
- Day Type
- Customer Segment

Dashboard นี้ช่วยให้สามารถมองเห็นภาพรวมของรายได้และ demand ได้ในหน้าเดียว และสนับสนุนการตัดสินใจเชิงธุรกิจได้อย่างมีประสิทธิภาพ

---

# 📁 11. Repository Structure

```bash
azure-stay-revenue-analysis/
├── analysis/
│   └── EDA_hotel_revenue_analysis.xlsx
├── data/
│   ├── raw/
│   │   ├── dim_calendar.csv
│   │   ├── dim_channels.csv
│   │   ├── dim_rate_codes.csv
│   │   ├── dim_room_inventory.csv
│   │   ├── dim_segments_clean.csv
│   │   └── fact_bookings_clean.csv
│   └── processed/
│       └── fact_bookings_enriched.csv
├── images/
│   ├── h1_channel_average_revenue.png
│   ├── h2_ratecode_average_revenue.png
│   ├── number_of_bookings_by_rate_code.png
│   ├── h3_daytype_bookings.png
│   ├── h3_daytype_revenue.png
│   ├── customer_segment_revenue_per_booking.png
│   ├── customer_segment_number_of_bookings.png
│   ├── revenue_vs_adults.png
│   ├── revenue_vs_commission.png
│   ├── true_room_revenue_distribution.png
│   └── eda_outlier_revenue.png
├── tableau/
│   └── azure_stay_dashboard.twbx
├── slides/
│   └── Azure_Stay_Revenue_Analysis.pdf
└── README.md
