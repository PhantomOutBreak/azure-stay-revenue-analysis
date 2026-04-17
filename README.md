## 📌 1. Background & Pain Points

Azure Stay กำลังเผชิญปัญหา **Revenue Stagnation**  
แม้มีจำนวนผู้เข้าพักในระดับดี แต่ค่า **RevPAR** ไม่เติบโตและไม่สอดคล้องกับต้นทุนที่เพิ่มขึ้น  
สะท้อนถึงความไม่มีประสิทธิภาพด้านการตั้งราคาและการบริหารห้องพัก

### ⚠️ Pain Points

- **Inefficient Pricing**  
  ราคาห้องไม่สอดคล้องกับ Demand ทำให้พลาดโอกาสเพิ่ม **ADR**

- **Poor Inventory Management**  
  การจัดการ **LOS และ BLT** ยังไม่เหมาะสม ทำให้ใช้ทรัพยากรไม่เต็มประสิทธิภาพ

- **Impact on Profitability**  
  RevPAR ต่ำ → กำไรลดลง, เสียโอกาสช่วง Peak และต้นทุนต่อห้องสูงขึ้น

> 💡 สรุป: RevPAR ต่ำกระทบทั้งรายได้ กำไร และความสามารถในการแข่งขัน

---

## 🎯 2. SMART Objectives

- **Specific:** เพิ่ม RevPAR ผ่าน Dynamic Pricing และการจัดการ LOS  
- **Measurable:** เพิ่ม RevPAR ≥ **15%**  
- **Achievable:** ใช้ BLT และ Demand วิเคราะห์เพื่อปรับราคา  
- **Relevant:** เสริมความสามารถในการแข่งขันและกำไรระยะยาว  
- **Time-bound:** ภายใน **6 เดือน**

---

## 🔬 3. คำถามทางธุรกิจ (Business Questions)
เพื่อวิเคราะห์ปัญหา Revenue Stagnation ของโรงแรม Azure Stay  
จึงได้กำหนดคำถามทางธุรกิจในมิติต่าง ๆ ดังนี้:

### 🔹 Channel
1. ช่องทางการจองใดสร้าง **RevPAR สูงสุด** และช่องทางใดมีปริมาณการจองสูงแต่ให้ผลตอบแทนต่ำ

### 🔹 Pricing
2. ประเภทราคา (Rate Code) ส่งผลต่อ **ADR และ Occupancy** อย่างไร  
3. การใช้โปรโมชั่นหรือส่วนลด ส่งผลต่อรายได้รวมในเชิงบวกหรือเชิงลบ

### 🔹 Time
4. ช่วงเวลา (Weekend vs Weekday) มีผลต่อระดับ Demand และรายได้หรือไม่

### 🔹 Customer
5. กลุ่มลูกค้า (Customer Segment) ใดสร้างรายได้สูง และกลุ่มใดมีประสิทธิภาพต่ำ

### 🔹 Strategy
6. โรงแรมมีการตั้งราคาห้องพักเหมาะสมกับระดับ Demand หรือไม่ โดยเฉพาะในช่วง High Demand

---

## 🧪 4. สมมติฐานการวิจัย (Hypotheses)

จากคำถามทางธุรกิจข้างต้น สามารถตั้งสมมติฐานเพื่อทดสอบได้ดังนี้:

### 🔹 H1: Channel Effect
คาดว่าช่องทาง OTA จะมีค่า RevPAR ต่ำกว่าช่องทาง Direct  
เนื่องจากมีค่าคอมมิชชั่นที่สูงกว่า ซึ่งส่งผลให้รายได้สุทธิต่อห้องลดลง

---

####🔹 H2: Pricing Effect
- วิเคราะห์ **ADR และ Net ADR รวมถึง Occupancy แยกตาม Rate Code**  
- เปรียบเทียบ Discount vs Non-discount  
- ตรวจสอบว่า Occupancy เพิ่มขึ้นแลกกับรายได้สุทธิที่ลดลงหรือไม่  

- **Net ADR** = (Total Room Revenue × (1 - Commission Rate)) / Number of Rooms Sold

---

### 🔹 H3: Demand Timing Effect
คาดว่าช่วงวันหยุดสุดสัปดาห์ (Weekend) จะมีระดับความต้องการ (Demand) สูงกว่าวันธรรมดา  
แต่โรงแรมยังไม่ได้ปรับราคาห้องพักให้สอดคล้องกับระดับ Demand ดังกล่าว

- - **Net RevPAR** = (Total Room Revenue × (1 - Commission Rate)) / Total Rooms Available

---

## ⚙️ 5. Methodology (วิธีการวิเคราะห์)

เพื่อทดสอบสมมติฐานที่ตั้งไว้ จะใช้การวิเคราะห์ข้อมูลเชิงสำรวจ (EDA) 
ร่วมกับการคำนวณตัวชี้วัดสำคัญ ดังนี้:

---

### 🔹 การคำนวณตัวชี้วัดหลัก (Key Metrics)

- **RevPAR (Revenue Per Available Room)**  
  = Total Room Revenue / Total Rooms Available  

- **ADR (Average Daily Rate)**  
  = Total Room Revenue / Number of Rooms Sold  

- **Occupancy Rate (OCC)**  
  = (Number of Rooms Sold / Total Rooms Available) × 100  

---

### 🔹 วิธีทดสอบสมมติฐาน

#### ✅ ทดสอบ H1: Channel Effect

- วิเคราะห์ **RevPAR และ Net RevPAR แยกตาม Booking Channel**  
- เปรียบเทียบระหว่าง OTA และ Direct  
- พิจารณาผลกระทบจาก Commission โดยคำนวณรายได้สุทธิหลังหักค่าคอมมิชชั่น  


---

#### ✅ ทดสอบ H2: Pricing Effect
- วิเคราะห์ **ADR และ Occupancy แยกตาม Rate Code**  
- เปรียบเทียบ Discount vs Non-discount  
- ตรวจสอบว่า Occupancy เพิ่มขึ้นแลกกับรายได้ที่ลดลงหรือไม่  

---

#### ✅ ทดสอบ H3: Demand Timing Effect
- วิเคราะห์ **Occupancy และ RevPAR แยกตาม Day of Week**  
- เปรียบเทียบ Weekend vs Weekday  
- ตรวจสอบว่ามีการตั้งราคาเหมาะสมกับ Demand หรือไม่  

---
