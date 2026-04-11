# 🏨 Azure Stay Revenue Analysis  
### การวิเคราะห์ปัจจัยที่ส่งผลต่อรายได้ต่อห้องพัก (RevPAR) และประสิทธิภาพการตั้งราคา

---

## 📌 ภาพรวมโครงการ (Project Overview)

โครงการนี้มุ่งวิเคราะห์ปัญหา **Revenue Stagnation** ของโรงแรม Azure Stay  
แม้ **Occupancy** อยู่ในระดับที่ดี แต่ **RevPAR** ไม่เติบโตตามศักยภาพเมื่อเทียบกับคู่แข่ง

เราใช้แนวคิด:
**Business Intelligence (BI)** · **Data Analytics** · **Exploratory Data Analysis (EDA)**  
เพื่อค้นหา *root cause* และเสนอแนวทางเพิ่มรายได้เชิงกลยุทธ์

---

## 🎯 วัตถุประสงค์ (Objectives)

- วิเคราะห์สาเหตุที่ทำให้ RevPAR ไม่เติบโต  
- ประเมินประสิทธิภาพ **Pricing Strategy** และ **Booking Channels**  
- ค้นหาโอกาสเพิ่ม **RevPAR** และ **ADR**  
- สร้างแนวทาง Dashboard เพื่อสนับสนุนการตัดสินใจ  

---

## 🚨 ปัญหาทางธุรกิจ (Business Problem)

แม้:
- จำนวนการจองดี  
- Occupancy สูง  

แต่:
- **RevPAR ต่ำกว่าคู่แข่ง**

### 🔍 สาเหตุที่เป็นไปได้
- ตั้งราคาต่ำเกินไปในช่วง Demand สูง  
- ใช้โปรโมชั่นมากเกินจำเป็น  
- พึ่งพา OTA (ค่าคอมสูง)  
- การแบ่ง Segment ลูกค้าไม่เหมาะสม  
- การบริหาร Inventory ยังไม่มีประสิทธิภาพ  

> **Goal:** เพิ่มรายได้โดยขาย “ห้องที่ใช่ ให้ลูกค้าที่ใช่ ในเวลาที่ใช่ ในราคาที่ใช่”

---

## 📊 SMART Objectives

- 📈 เพิ่ม **RevPAR ≥ 10% ภายใน 3 เดือน**  
- 💰 ปรับปรุง **ADR** ผ่าน Rate Code Optimization  
- 📉 ลดการพึ่งพา OTA อย่างน้อย **15%**  
- 📅 ระบุช่วง Demand สูงและปรับ Pricing ให้เหมาะสม  
- 🧠 สร้าง Insight เพื่อใช้ตัดสินใจเชิงกลยุทธ์  

---

## ❓ คำถามทางธุรกิจ (Business Questions)

- ช่องทางใดสร้าง **RevPAR สูงสุดจริง**  
- ช่องทางใดมี Volume สูง แต่กำไรต่ำ  
- Rate Code ใดทำให้ ADR ลดลง  
- มีช่วงเวลาใดที่ “ตั้งราคาต่ำเกินไป”  
- Customer Segment ใดมี Performance ต่ำ  
- ควรปรับ Strategy อย่างไรเพื่อเพิ่มรายได้  

---

## 🧪 สมมติฐานการวิจัย (Hypotheses)

### 🔹 H1: Channel Effect
> OTA มี RevPAR สุทธิต่ำกว่าช่องทาง Direct  
เนื่องจากมีค่าคอมมิชชั่นสูง แม้จะมีจำนวนการจองมาก

### 🔹 H2: Pricing Effect
> Rate Code ที่มีส่วนลดช่วยเพิ่ม Occupancy  
แต่ทำให้ ADR และรายได้สุทธิลดลง

### 🔹 H3: Demand Timing Effect
> Weekend มี Demand สูง  
แต่ยังตั้งราคาไม่สอดคล้องกับ Demand

---
