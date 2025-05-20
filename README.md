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

![Time Conversion](![9208bf28-95ce-4f7a-ad57-36b25e2b915f png](https://github.com/user-attachments/assets/425ebe96-2596-4b1d-9241-643f145daeb7)
)
![Recency & Tenure Combined]![(ba3babf7-3186-496c-867d-048c4839d014 png](https://github.com/user-attachments/assets/5f93eec8-561b-4535-b22c-d50d420a9ea4)


---

## 💰 Monetary (Total Spending)

To calculate **Monetary**, find the **total revenue** per customer.

![Revenue in Main Table](![2647e811-1fc7-4ca3-bb22-a06ea1c3726a png (2)](https://github.com/user-attachments/assets/a4a6460b-d187-493c-92ee-c0c8d83016bc)
)
![Revenue by Customer])![8c0528ce-516c-4998-8385-8fffea7951e8 png](https://github.com/user-attachments/assets/e8afe728-8b14-486f-b761-aa9f389eabe7)



---

## 🔁 Frequency: Number of Purchases

We count unique **Invoice + Customer ID** pairs.

![Invoice Count Logic]![0697a3bd-f195-4654-ae20-8baa0b0eda4d png](https://github.com/user-attachments/assets/c1a9a3c5-2c8f-4032-b16d-70816502d1dd)

![Duplicate Invoice Copy]![0d0eca93-a313-4e01-8e2a-bf9872ef4e67 png](https://github.com/user-attachments/assets/b26c837a-cc0c-4b71-a4d1-80764a89348c)
)
![Remove Duplicates]![0d0eca93-a313-4e01-8e2a-bf9872ef4e67 png](https://github.com/user-attachments/assets/20f23f6e-7883-4c4a-84fa-e5d753ac1a20)
)

Explanation:
- Count of how many times a customer has purchased.
- One invoice = one purchase, regardless of how many products.

![Frequency Table]![9601f638-49d7-4e6f-ae12-c289e7794985 png](https://github.com/user-attachments/assets/18ade743-ffb4-4bb0-9da0-f8ecaca9aadb)
)
![Customer Frequency Example]![59ddb04c-a22a-4ccf-8361-b37d588e163b png](https://github.com/user-attachments/assets/c76b1c94-29fe-4765-b57f-da8a497e8d1c)

![Final Frequency View]![abd81594-e002-4da6-bbd9-3e14c8c02866 png](https://github.com/user-attachments/assets/af4d6a48-c966-467f-8ffc-d554bb38e908)
()

---

## 🧺 Basket Size: Average Spend Per Purchase

**Basket Size = Monetary / Frequency**

![Basket Size Explanation]![13eb8299-74ea-4c98-b1cb-448690a4e2ee png](https://github.com/user-attachments/assets/1d5f2fa9-5b0e-48e2-8801-fd8cf539558a)
)
![Basket Size Table]![ee65d48f-8977-4d55-881f-86513599314d png](https://github.com/user-attachments/assets/81c44184-f7f9-4398-95a6-d619c515a0dc)
)

Interpretation:
- High = bulk or corporate buyers
- Low = frequent small purchases

