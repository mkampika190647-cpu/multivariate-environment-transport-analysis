# Multivariate Analysis on Environmental & Transportation Trends

**Applied Multivariate Analysis Project | R · Cluster Analysis · K-Means · Discriminant Analysis · Data Visualization**

## Project Overview

โครงงานนี้เป็นการประยุกต์ใช้เทคนิคการวิเคราะห์พหุตัวแปร (Multivariate Analysis)
เพื่อศึกษารูปแบบและจัดกลุ่มประเทศจากข้อมูลด้านสิ่งแวดล้อมและการคมนาคม

ชุดข้อมูลที่ใช้ในการวิเคราะห์ประกอบด้วยข้อมูลจาก **91 ประเทศ**
และตัวแปรเชิงปริมาณ 4 ตัวแปร ได้แก่ `GHG_Value`, `SA_Value`,
`GCI_Value` และ `Air_Value`

การวิเคราะห์ดำเนินการด้วยโปรแกรม R โดยใช้เทคนิค
Hierarchical Clustering, K-Means Clustering และ Discriminant Analysis
เพื่อค้นหารูปแบบความคล้ายคลึงระหว่างประเทศและศึกษาความสามารถในการจำแนกกลุ่ม

## Objectives

- ศึกษาลักษณะของข้อมูลด้านสิ่งแวดล้อมและการคมนาคมในแต่ละประเทศ
- จัดกลุ่มประเทศที่มีลักษณะคล้ายคลึงกันด้วย Cluster Analysis
- เปรียบเทียบผลการจัดกลุ่มด้วย Hierarchical Clustering และ K-Means Clustering
- ใช้ Discriminant Analysis เพื่อศึกษาการจำแนกประเทศตามกลุ่มที่ได้
- ประยุกต์ใช้เทคนิค Multivariate Analysis กับข้อมูลจริง

## Dataset

ข้อมูลที่ใช้ในการวิเคราะห์ประกอบด้วย **91 ประเทศ และ 4 ตัวแปรหลัก**

| Variable | Description |
|---|---|
| `GHG_Value` | ตัวแปรด้านการปล่อยก๊าซเรือนกระจก |
| `SA_Value` | ตัวแปรด้านการเข้าถึง/การเดินทาง |
| `GCI_Value` | ตัวแปรดัชนีที่เกี่ยวข้องกับการคมนาคม |
| `Air_Value` | ตัวแปรด้านการเดินทางทางอากาศ |

ก่อนการวิเคราะห์มีการเตรียมข้อมูลและตรวจสอบตัวแปร
เพื่อให้เหมาะสมสำหรับการวิเคราะห์พหุตัวแปร

## Methodology

กระบวนการวิเคราะห์หลักประกอบด้วย

1. เตรียมและตรวจสอบข้อมูล
2. สำรวจลักษณะของตัวแปร
3. ปรับมาตรฐานข้อมูลสำหรับการจัดกลุ่ม
4. วิเคราะห์ด้วย Hierarchical Clustering
5. วิเคราะห์ด้วย K-Means Clustering
6. เปรียบเทียบและตีความลักษณะของแต่ละกลุ่ม
7. วิเคราะห์ต่อด้วย Discriminant Analysis
8. สรุปและนำเสนอผลการวิเคราะห์

## Hierarchical Clustering

ใช้ Hierarchical Clustering เพื่อศึกษาความคล้ายคลึงและความแตกต่าง
ระหว่างประเทศจากตัวแปรหลายตัวพร้อมกัน

ผลการวิเคราะห์สามารถแสดงในรูปแบบ Dendrogram
เพื่อช่วยพิจารณาโครงสร้างและการรวมกลุ่มของประเทศ

## K-Means Clustering

ใช้ K-Means Clustering เพื่อแบ่งประเทศออกเป็นกลุ่ม
ตามลักษณะของข้อมูลด้านสิ่งแวดล้อมและการคมนาคม

ผลการวิเคราะห์แบ่งข้อมูลออกเป็น **4 กลุ่ม**

- Cluster 1 — 46 ประเทศ
- Cluster 2 — 32 ประเทศ
- Cluster 3 — 12 ประเทศ
- Cluster 4 — 1 ประเทศ

จากนั้นจึงศึกษาลักษณะของแต่ละ Cluster
เพื่อเปรียบเทียบความแตกต่างของประเทศในแต่ละกลุ่ม

## Discriminant Analysis

หลังจากการจัดกลุ่มข้อมูล ได้ประยุกต์ใช้ Discriminant Analysis
เพื่อศึกษาความสามารถในการจำแนกประเทศเข้าสู่กลุ่มต่าง ๆ
โดยอาศัยตัวแปรที่ใช้ในการวิเคราะห์

ขั้นตอนนี้ช่วยให้สามารถศึกษาความแตกต่างระหว่างกลุ่ม
และประเมินรูปแบบการจำแนกจากข้อมูลพหุตัวแปรได้

## Analysis Techniques

- Descriptive Data Analysis
- Data Standardization
- Hierarchical Clustering
- Dendrogram Analysis
- K-Means Clustering
- Cluster Interpretation
- Discriminant Analysis
- Multivariate Data Visualization

## Tools & Technologies

- R
- RStudio
- Statistical Analysis
- Multivariate Analysis
- Data Visualization

## Project Activities

โปรเจกต์นี้เป็นงานกลุ่มในรายวิชา Applied Multivariate Analysis
โดยสมาชิกในกลุ่มร่วมกันดำเนินการวิเคราะห์และจัดทำรายงาน ซึ่งครอบคลุมกิจกรรมดังนี้

- เตรียมและตรวจสอบข้อมูลสำหรับการวิเคราะห์
- วิเคราะห์ข้อมูลด้วยโปรแกรม R
- ประยุกต์ใช้ Hierarchical Clustering และ K-Means Clustering
- วิเคราะห์และเปรียบเทียบลักษณะของแต่ละ Cluster
- ประยุกต์ใช้ Discriminant Analysis สำหรับการจำแนกกลุ่ม
- สร้างกราฟและ Visualization เพื่อประกอบการวิเคราะห์
- ตีความและสรุปผลการวิเคราะห์ทางสถิติ
- จัดทำรายงานและนำเสนอผลการวิเคราะห์

## Project Report

รายละเอียดเกี่ยวกับชุดข้อมูล ขั้นตอนการวิเคราะห์
ผลการจัดกลุ่ม และ Discriminant Analysis สามารถดูได้จากรายงานฉบับเต็ม

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

โครงงานนี้จัดทำขึ้นเพื่อประยุกต์ใช้เทคนิคทางสถิติพหุตัวแปร
กับข้อมูลจริง โดยเน้นการจัดกลุ่ม การจำแนกกลุ่ม
การตีความผลทางสถิติ และการนำเสนอผลการวิเคราะห์

> **Note:** Repository นี้จัดทำขึ้นเพื่อการศึกษาและการนำเสนอผลงานใน Portfolio
