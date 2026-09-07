# Multivariate Analysis on Environmental & Transportation Trends

**Applied Multivariate Analysis | R · RStudio · Cluster Analysis · K-Means · Discriminant Analysis**

โปรเจกต์วิเคราะห์ข้อมูลพหุตัวแปรเพื่อศึกษาความแตกต่างของประเทศจากข้อมูลด้านสิ่งแวดล้อมและโครงสร้างพื้นฐานด้านการคมนาคม โดยใช้ข้อมูลจาก 91 ประเทศ และประยุกต์ใช้ Cluster Analysis และ Discriminant Analysis ในการจัดกลุ่มและศึกษาความแตกต่างระหว่างกลุ่มประเทศ

## Project Overview

ข้อมูลที่ใช้ในการวิเคราะห์ประกอบด้วยข้อมูลจาก **91 ประเทศ** และตัวแปรเชิงปริมาณ 4 ตัวแปร ได้แก่ `GHG_Value`, `SA_Value`, `GCI_Value` และ `Air_Value`

ก่อนการจัดกลุ่ม ข้อมูลถูกตรวจสอบและปรับมาตรฐานด้วย Z-score เนื่องจากตัวแปรแต่ละตัวมีหน่วยและช่วงค่าที่แตกต่างกัน

การวิเคราะห์แบ่งออกเป็น 2 ส่วนหลัก ได้แก่ Cluster Analysis และ Discriminant Analysis โดยในส่วนของ Cluster Analysis มีการเปรียบเทียบผลจาก Hierarchical Clustering และ K-Means Clustering และใช้ผลการจัดกลุ่มเป็นพื้นฐานในการศึกษาความแตกต่างระหว่างกลุ่มด้วย Discriminant Analysis

## Objectives

- จัดกลุ่มประเทศจากตัวแปรด้านสิ่งแวดล้อมและโครงสร้างพื้นฐานด้านการคมนาคม
- เปรียบเทียบผลการจัดกลุ่มด้วย Hierarchical Clustering และ K-Means Clustering
- ศึกษาลักษณะของประเทศในแต่ละกลุ่ม
- ใช้ Discriminant Analysis เพื่อศึกษาความแตกต่างและการจำแนกกลุ่มประเทศ
- ประยุกต์ใช้เทคนิค Multivariate Analysis กับข้อมูลจริง

## Dataset

ข้อมูลที่ใช้ในการวิเคราะห์ประกอบด้วย **91 ประเทศ และ 4 ตัวแปรหลัก**

| Variable | Description | Unit / Scale |
|---|---|---|
| `GHG_Value` | ปริมาณการปล่อยก๊าซเรือนกระจกจากภาคการขนส่ง | MtCO2 |
| `SA_Value` | ความหนาแน่นของถนน | km/km² |
| `GCI_Value` | คะแนนด้านโครงสร้างพื้นฐานการขนส่ง (GCI) | 0–100 |
| `Air_Value` | คะแนนรวมด้านความเชื่อมโยงของสนามบิน | k |

ข้อมูลผ่านการทำความสะอาดและตรวจสอบ Missing Values ก่อนนำไปวิเคราะห์

## Data Preparation

ก่อนทำ Cluster Analysis มีการตรวจสอบโครงสร้างและการกระจายของข้อมูล รวมถึง Missing Values และความสัมพันธ์ระหว่างตัวแปร

เนื่องจากตัวแปรมีหน่วยวัดแตกต่างกัน จึงทำ **Z-score Standardization** ก่อนคำนวณระยะทางและจัดกลุ่ม เพื่อให้ตัวแปรที่มีช่วงค่ามากไม่ส่งผลต่อการจัดกลุ่มมากเกินไป

จากการสำรวจข้อมูลพบว่า `GHG_Value` และ `Air_Value` มีการกระจายแบบเบ้และมีค่าผิดปกติค่อนข้างสูง ซึ่งเป็นข้อสังเกตสำคัญในการตีความผลของ Cluster Analysis

## Hierarchical Clustering

ใช้ **Hierarchical Clustering** โดยคำนวณระยะห่างด้วย **Euclidean Distance** และใช้วิธี **Ward.D2** สำหรับการรวมกลุ่ม

จาก Dendrogram แบ่งข้อมูลออกเป็น **4 Clusters** ได้แก่

- Cluster 1 — 73 ประเทศ
- Cluster 2 — 6 ประเทศ
- Cluster 3 — 8 ประเทศ
- Cluster 4 — 4 ประเทศ

ผลจาก Hierarchical Clustering ใช้เพื่อศึกษาความใกล้ชิดและโครงสร้างการรวมกลุ่มของประเทศจากตัวแปรทั้ง 4 ตัว

## K-Means Clustering

ใช้ **Elbow Method** เพื่อพิจารณาจำนวน Cluster ที่เหมาะสม และเลือก **k = 4** สำหรับการวิเคราะห์ด้วย K-Means

ผลการจัดกลุ่มด้วย K-Means แบ่งประเทศออกเป็น

- Cluster 1 — 46 ประเทศ
- Cluster 2 — 32 ประเทศ
- Cluster 3 — 12 ประเทศ
- Cluster 4 — 1 ประเทศ

ค่า Between-Cluster Sum of Squares เทียบกับ Total Sum of Squares อยู่ที่ประมาณ **56.7%** แสดงถึงสัดส่วนความแตกต่างระหว่างกลุ่มที่ได้จากการจัดกลุ่ม

เมื่อพิจารณาค่า Centroid ในรูป Z-score พบว่าแต่ละ Cluster มีลักษณะแตกต่างกันตามระดับของตัวแปรที่ใช้ในการวิเคราะห์ และ Cluster 4 มีเพียง 1 ประเทศ ซึ่งมีค่า `GHG_Value` สูงกว่ากลุ่มอื่นอย่างชัดเจน

## Hierarchical vs K-Means

ทั้ง Hierarchical Clustering และ K-Means แบ่งข้อมูลออกเป็น 4 กลุ่ม แต่จำนวนประเทศและองค์ประกอบของแต่ละกลุ่มแตกต่างกัน

Hierarchical Clustering มีกลุ่มหลักขนาดใหญ่ 73 ประเทศ ขณะที่ K-Means กระจายข้อมูลออกเป็นกลุ่มขนาด 46, 32, 12 และ 1 ประเทศ

ผลจาก K-Means ยังทำให้เห็นกลุ่มที่มีลักษณะเป็น Outlier ได้ชัดเจน โดย Cluster 4 มีเพียงประเทศเดียวและมีค่า `GHG_Value` สูงมากเมื่อเทียบกับประเทศอื่น

## Discriminant Analysis

หลังจากการจัดกลุ่ม มีการใช้ **Linear Discriminant Analysis (LDA)** เพื่อศึกษาการจำแนกประเทศตามกลุ่ม โดยใช้ตัวแปร `GHG_Value`, `SA_Value`, `GCI_Value` และ `Air_Value`

ผลการวิเคราะห์พบว่า `GCI_Value` และ `GHG_Value` เป็นตัวแปรหลักที่มีบทบาทในการจำแนกกลุ่ม ขณะที่ `SA_Value` และ `Air_Value` มีบทบาทรองลงมา

จากการตรวจสอบผลการจำแนกด้วย Confusion Matrix พบว่าแบบจำลองสามารถจำแนกกลุ่มได้ถูกต้องมากกว่า **80%**

ผลจาก Discriminant Plot ยังช่วยแสดงความแตกต่างระหว่างกลุ่ม โดยเฉพาะกลุ่มที่มีค่า `GHG_Value` สูงผิดปกติซึ่งแยกออกจากกลุ่มอื่นได้ค่อนข้างชัดเจน

## Key Findings

จากการวิเคราะห์พบว่าสามารถแบ่งประเทศออกเป็น **4 กลุ่ม** ได้ทั้งจาก Hierarchical Clustering และ K-Means แม้จำนวนประเทศในแต่ละกลุ่มจะแตกต่างกัน

K-Means แสดงการแบ่งกลุ่มที่ทำให้เห็นความแตกต่างของลักษณะประเทศได้ชัดขึ้น และพบ Cluster ที่มีเพียง 1 ประเทศซึ่งมีค่า `GHG_Value` สูงกว่าประเทศอื่นอย่างมาก

สำหรับ Discriminant Analysis พบว่า `GCI_Value` และ `GHG_Value` เป็นตัวแปรสำคัญในการจำแนกกลุ่ม และผลการจำแนกมีความถูกต้องมากกว่า 80%

## Limitations

ข้อมูลบางตัวแปร โดยเฉพาะ `GHG_Value` และ `Air_Value` มีการกระจายแบบเบ้และมี Outliers ซึ่งอาจส่งผลต่อผลการจัดกลุ่ม

นอกจากนี้ ขนาดของบางกลุ่มมีจำนวนประเทศค่อนข้างน้อย ซึ่งอาจส่งผลต่อเสถียรภาพของ Discriminant Analysis และการวิเคราะห์ใช้ตัวแปรเพียง 4 ตัว จึงยังไม่ครอบคลุมปัจจัยอื่นที่อาจช่วยอธิบายความแตกต่างระหว่างประเทศได้

แนวทางสำหรับการวิเคราะห์เพิ่มเติมสามารถพิจารณาการ Transform ตัวแปรที่มีการกระจายเบ้ เพิ่มตัวแปรที่เกี่ยวข้อง ทดลองใช้ PCA เพื่อลดมิติก่อนทำ Cluster Analysis และใช้ Cross-validation เพื่อตรวจสอบความสามารถในการจำแนกของแบบจำลอง

## Analysis Techniques

- Descriptive Statistics
- Data Standardization
- Correlation Analysis
- Hierarchical Clustering
- Euclidean Distance
- Ward.D2 Method
- Dendrogram Analysis
- Elbow Method
- K-Means Clustering
- Cluster Interpretation
- Linear Discriminant Analysis
- Confusion Matrix
- Multivariate Data Visualization

## Tools & Technologies

- R
- RStudio
- Cluster Analysis
- Discriminant Analysis
- Data Visualization

## Project Activities

โปรเจกต์นี้เป็น **Academic Team Project** ในรายวิชา Applied Multivariate Analysis โดยสมาชิกในกลุ่มร่วมกันเตรียมข้อมูล วิเคราะห์ และจัดทำรายงาน

งานในโปรเจกต์ครอบคลุมการตรวจสอบและปรับมาตรฐานข้อมูล การวิเคราะห์ Hierarchical Clustering และ K-Means การเปรียบเทียบลักษณะของแต่ละ Cluster การวิเคราะห์ Discriminant Analysis รวมถึงการสร้างกราฟและตีความผลทางสถิติ

## Project Report

รายละเอียดของข้อมูล ขั้นตอนการวิเคราะห์ ผลการจัดกลุ่ม และ Discriminant Analysis สามารถดูได้จากรายงานฉบับเต็ม

[View Full Project Report](Multivariate%20Analysis%20on%20Environmental%20%26%20Transportation%20Trends.pdf)

## Project Structure

```text
multivariate-environment-transport-analysis/
│
├── README.md
└── Multivariate Analysis on Environmental & Transportation Trends.pdf
```

## Project Type

**Academic Project — Applied Multivariate Analysis**

โปรเจกต์นี้จัดทำขึ้นเพื่อประยุกต์ใช้เทคนิคการวิเคราะห์พหุตัวแปรกับข้อมูลระดับประเทศ ตั้งแต่การเตรียมและปรับมาตรฐานข้อมูล การจัดกลุ่มด้วย Hierarchical Clustering และ K-Means ไปจนถึงการวิเคราะห์การจำแนกกลุ่มด้วย Discriminant Analysis

> **Note:** Repository นี้จัดทำขึ้นเพื่อการศึกษาและการนำเสนอผลงานใน Portfolio
