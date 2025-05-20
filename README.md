# RFM-Excel-Analysis
EXCEL FILES google drive link : https://docs.google.com/spreadsheets/d/1Y6915wKTMTDHMFVo4IYOpm0R9TS6bjGS/edit?usp=drive_link&ouid=102618739620148941630&rtpof=true&sd=true
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
🔍 What is FREQUENCY?
FREQUENCY refers to how many times a customer made a purchase within a given time period.

✅ How Is It Calculated?
Let’s consider a sample sales dataset:

Customer ID	Invoice ID
12346	INV001
12347	INV002
12347	INV003
12347	INV004
12348	INV005

12346: made only 1 purchase → Frequency = 1

12347: made 3 purchases → Frequency = 3

12348: made 1 purchase → Frequency = 1

To calculate this:

Group the dataset by Customer ID

Count how many times each customer appears = number of purchases

📄 Example Excel Formula:
excel
Kopyala
Düzenle
=COUNTIF(CustomerColumn, [CustomerID])
📌 Why Did We Duplicate by CUSTOMER ID?
As seen in your second screenshot:

The left column contains unique Customer IDs

The right column shows their corresponding purchase frequency, calculated using COUNTIF

To bring this back into the main dataset:

Use VLOOKUP or INDEX-MATCH to map frequency back based on Customer ID

🧠 Why Do We Do This?
Because:

Each row in the main table represents a transaction

But FREQUENCY is a customer-level metric (how often they came)

So we first calculate frequency per customer, and then merge it back to each transaction related to that customer

🧪 Practical Example:
Let’s say we have this data:

Customer ID	Invoice ID
111	A
111	B
222	C
111	D
222	E

Excel Formula:
excel
Kopyala
Düzenle
=COUNTIF(A:A, A2)
This gives us:

Customer ID	Frequency
111	3
222	2

Now, when you merge this frequency table back into your main dataset, each transaction row will also show how many times that customer has purchased in total.

📌 Summary:
FREQUENCY = Number of times a Customer ID appears (number of purchases)

Calculated using COUNTIF

Create a frequency list per customer

Merge back into the main dataset using VLOOKUP or INDEX MATCH


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

🧺 What is Basket Size?
Basket Size shows how much a customer spends on average per transaction.

In other words:

"How much does a customer spend in a single purchase on average?"

📌 Formula:
excel
Kopyala
Düzenle
Basket Size = Monetary / Frequency
Example:
The customer has spent a total of 1000 TL (Monetary)

And made 4 purchases (Frequency)

👉 Basket Size = 1000 / 4 = 250 TL

📈 Why Is It Useful?
High basket size → The customer spends a large amount per visit. Could be a wholesaler or a corporate client.

Low basket size → The customer shops more frequently but spends less per visit. Might be a discount chaser or a retail customer.

This metric is highly useful for:

Customer segmentation

Targeted campaigns

Loyalty analysis

✅ Excel Application:
From your example:

Monetary	Frequency	Basket Size
77.184	1	= 77.184
4.310	7	≈ 0.6157...
1.797	4	≈ 0.44925...

Excel Formula:
excel
Kopyala
Düzenle
=E2 / D2
(Assuming Monetary is in column E, and Frequency is in column D)

🎯 Summary:
Basket Size = Monetary / Frequency

It tells the average amount spent per transaction

Helps us understand customer spending behavior more clearly
