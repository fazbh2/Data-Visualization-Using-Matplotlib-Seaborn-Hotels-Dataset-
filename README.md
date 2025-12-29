# Data-Visualization-Using-Matplotlib-Seaborn-Hotels-Dataset-
This project demonstrates data visualization techniques using Matplotlib and Seaborn on a Hotels dataset. The goal is to understand booking patterns, prices, and customer behavior through graphs.
Sample Hotels Dataset Columns

(typical structure)

hotel – Hotel type (City Hotel / Resort Hotel)

is_canceled – Booking canceled (0 = No, 1 = Yes)

lead_time – Days between booking and arrival

adr – Average Daily Rate (price)

arrival_date_month

stays_in_weekend_nights

stays_in_week_nights

adults, children

🔹 Libraries Used
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns

📌 Load the Dataset
df = pd.read_csv("hotels.csv")
df.head()

📈 Matplotlib Visualizations
1️⃣ Number of Bookings by Hotel Type
hotel_counts = df['hotel'].value_counts()

plt.figure()
plt.bar(hotel_counts.index, hotel_counts.values)
plt.xlabel("Hotel Type")
plt.ylabel("Number of Bookings")
plt.title("Bookings by Hotel Type")
plt.show()


📌 Insight: City hotels usually receive more bookings than resort hotels.

2️⃣ Average Price (ADR) Comparison
avg_price = df.groupby('hotel')['adr'].mean()

plt.figure()
plt.plot(avg_price.index, avg_price.values, marker='o')
plt.xlabel("Hotel Type")
plt.ylabel("Average Daily Rate")
plt.title("Average Price by Hotel Type")
plt.show()


📌 Insight: Resort hotels often have higher average prices.

📊 Seaborn Visualizations
3️⃣ Booking Cancellation Distribution
sns.countplot(x='is_canceled', data=df)
plt.title("Booking Cancellation Count")
plt.xlabel("Canceled (0 = No, 1 = Yes)")
plt.ylabel("Count")
plt.show()


📌 Insight: Helps analyze cancellation trends.

4️⃣ Price Distribution (ADR)
sns.histplot(df['adr'], bins=30, kde=True)
plt.title("Distribution of Average Daily Rate")
plt.xlabel("ADR")
plt.show()


📌 Insight: Most bookings fall within a specific price range.

5️⃣ Monthly Booking Trends
plt.figure()
sns.countplot(x='arrival_date_month', data=df,
              order=df['arrival_date_month'].value_counts().index)
plt.xticks(rotation=45)
plt.title("Bookings per Month")
plt.show()


📌 Insight: Identifies peak booking months.

6️⃣ Relationship Between Lead Time and Price
sns.scatterplot(x='lead_time', y='adr', data=df)
plt.title("Lead Time vs Price")
plt.xlabel("Lead Time (Days)")
plt.ylabel("ADR")
plt.show()


📌 Insight: Early bookings may show price variation.

🎯 Conclusion

Using Matplotlib and Seaborn, we can:

Compare hotel performance

Analyze cancellations

Understand pricing patterns

Identify seasonal booking trends

These visualizations help hotels improve pricing strategies and customer retention.

🚀 Tools & Technologies

Python

Pandas

Matplotlib

Seaborn

Jupyter Notebook / VS Code

Visualizations
🔸 Bookings by Hotel Type (Matplotlib)
🔸 Average Daily Rate Comparison
🔸 Booking Cancellation Analysis (Seaborn)
🔸 Price Distribution
🔸 Monthly Booking Trends
🔸 Lead Time vs Price Relationship

Each visualization provides insights into hotel performance and customer behavior.

🎯 Conclusion

Matplotlib and Seaborn make it easy to:

Understand booking patterns

Analyze cancellations

Study pricing distribution

Identify seasonal trends

This analysis helps hotels make data-driven business decisions.

👨‍💻 Author

Name: Faizan Bhat
Role: Python & Data Science Learner
Tools: Python, Pandas, Matplotlib, Seaborn
