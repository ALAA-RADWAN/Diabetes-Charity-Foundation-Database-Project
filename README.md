<h1 align="center">Diabetes Charity Foundation – Database Project</h1>

<p align="center">
A complete relational database system designed for a medical charity supporting diabetes awareness, education, fundraising, and research.
</p>

---

## 📌 Project Overview

A database designed to help the Diabetes Charity Foundation track:
- Donors  
- Campaigns  
- Donations  
- Education sessions  
- Research grants  

The system answers key questions such as:
- Who donates the most?
- Which campaigns raise the highest amounts?
- How many sessions are delivered?
- Which research projects receive major funding?

---
### **ER Diagram**

<img width="1004" height="580" alt="image" src="https://github.com/user-attachments/assets/30fb580a-4076-4a5f-a86a-766aa1d3abd9" />

---

## 🧩 Scenario & Example Queries

1. Donors who donated more than **£500**  
2. Donations per campaign  
3. Sessions under **“Diabetes Awareness Week 2026”**  
4. Sessions per location  
5. Research grants above **£10,000**  

---

## 🗺️ ER Model

**Entities:**
- Donor  
- Campaign  
- Donation  
- Education_Session  
- Research_Grant  

**Relationships:**
- Donor → Donation (1:M)  
- Campaign → Donation (1:M)  
- Campaign → Education_Session (1:M)  
- Campaign → Research_Grant (1:M)  

---

## 🧱 Relational Schema

<img width="482" height="184" alt="image" src="https://github.com/user-attachments/assets/3eebd08f-602a-4413-9d8f-28ca2fdc11e9" />

<img width="386" height="329" alt="image" src="https://github.com/user-attachments/assets/f2445d0d-15b3-4c7f-8be1-4207806b118b" />

<img width="395" height="199" alt="image" src="https://github.com/user-attachments/assets/c143e191-2c27-4a00-a1d7-63f10f61f19d" />

<img width="406" height="179" alt="image" src="https://github.com/user-attachments/assets/40a340ae-3631-4775-b945-287a180cb0d8" />



---

## 🗄️ Sample Data

<img width="425" height="294" alt="image" src="https://github.com/user-attachments/assets/80f0eea6-1b7a-4f1b-9f51-5c6b89b4c9d7" />

<img width="426" height="344" alt="image" src="https://github.com/user-attachments/assets/cebc69a7-f1b9-4c5d-856c-21dac2b0c785" />

---

## 🔍 SQL Queries

### **Query Results (phpMyAdmin)**
#### Query 1 – Donors > £500
<img width="965" height="576" alt="image" src="https://github.com/user-attachments/assets/5a6986e2-1fe2-488b-a216-dac15e47a086" />


#### Query 2 – Donations per Campaign
<img width="925" height="620" alt="image" src="https://github.com/user-attachments/assets/d215c657-f20d-4308-9530-0774ec1b51c2" />


#### Query 3 – Sessions under Awareness Week
<img width="940" height="621" alt="image" src="https://github.com/user-attachments/assets/56fd2748-f91d-4a71-9096-6289ccd31bf9" />


#### Query 4 – Sessions per Location
<img width="940" height="540" alt="image" src="https://github.com/user-attachments/assets/7526a8f3-0bf7-4b90-aed9-cbc065b8c50a" />


---
## 🗃️ NoSQL Discussion

If the data was stored in a non‑relational database, the structure of the system will look very different from the relational version. In a relational database, everything must be in fixed tables. A NoSQL database does not need a fixed schema, so the data can grow and change more easily. This is useful, because for example in the case of the charity’s dataset new types of campaigns, sessions, or research may appear over time. Also, the suitable type of NoSQL database will be a document‑oriented database (such as MongoDB), and store information as JSON documents. These documents can contain different fields, nested objects, and lists. 

To explain this, for example, a campaign document will include the campaign name, start date, target amount, and list of sessions inside it. Each session can have its own small document with the title, date, and location. Donations and research grants can also be stored as embedded documents. This keeps related information together.

Moreover, NoSQL databases scale horizontally, meaning we can add more servers easily when the data grows. They are also distributed across multiple locations and have built‑in replication, so the system keeps running even if one server fails. 

Finally, using a document‑oriented NoSQL database will make the data flexible and easier to update. The JSON structure matches the data, and the scalability and reliability features make NoSQL a good choice for handling growing and changing data. An example if I will use document‑oriented NoSQL database for the charity’s data and create the Donor document by JSON:

{
  "DonorID": 1,
  "DonorName": " Ani Bro ",
  "Email": "a.b@example.org",
  "City": "London",
  "Donations": [
    {
      "DonationID": 11,
      "CampaignID": 20,
      "Amount": 150,
      "DonationDate": "2026-04-08"
    }
  ]
}

---



