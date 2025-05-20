# RFM-Excel-Analysis

# 🛍️ RFM Analysis with Excel

## 📅 Recency: Time Since Last Purchase

We calculate **Recency** as the difference between **today’s date** and the **most recent purchase date**.

![Recency Calculation](![image](https://github.com/user-attachments/assets/64c24115-5cd4-4bd8-b37e-cbd0ad1a81ea)

![Fixed Date](![image1](https://github.com/user-attachments/assets/541861ea-5bac-4af2-ab5e-512319c179bf)

![Recency Formula]![image3](https://github.com/user-attachments/assets/8b27e42d-17af-495e-b0fa-71611ae8fc51)


---

## ⌛ Recency vs Tenure

- **Minimum date** gives us **Recency**.
- **Maximum date** gives us **Tenure**.

![Time Conversion](9208bf28-95ce-4f7a-ad57-36b25e2b915f.png)
![Recency & Tenure Combined](ba3babf7-3186-496c-867d-048c4839d014.png)
![Added to Table](ebb063ac-aa79-460a-91e4-eed47dc09b64.png)

---

## 💰 Monetary (Total Spending)

To calculate **Monetary**, find the **total revenue** per customer.

![Revenue in Main Table](2647e811-1fc7-4ca3-bb22-a06ea1c3726a.png(2))
![Revenue by Customer](8c0528ce-516c-4998-8385-8fffea7951e8.png)


---

## 🔁 Frequency: Number of Purchases

We count unique **Invoice + Customer ID** pairs.

![Invoice Count Logic](0697a3bd-f195-4654-ae20-8baa0b0eda4d.png)
![Duplicate Invoice Copy](0d0eca93-a313-4e01-8e2a-bf9872ef4e67.png)
![Remove Duplicates](0d0eca93-a313-4e01-8e2a-bf9872ef4e67.png)

Explanation:
- Count of how many times a customer has purchased.
- One invoice = one purchase, regardless of how many products.

![Frequency Table](9601f638-49d7-4e6f-ae12-c289e7794985.png)
![Customer Frequency Example](59ddb04c-a22a-4ccf-8361-b37d588e163b.png)
![Final Frequency View](abd81594-e002-4da6-bbd9-3e14c8c02866.png)

---

## 🧺 Basket Size: Average Spend Per Purchase

**Basket Size = Monetary / Frequency**

![Basket Size Explanation](13eb8299-74ea-4c98-b1cb-448690a4e2ee.png)
![Basket Size Table](ee65d48f-8977-4d55-881f-86513599314d.png)

Interpretation:
- High = bulk or corporate buyers
- Low = frequent small purchases

