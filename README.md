# 📸 **Cracking Instagram Influence: Anomaly Detection & Growth Forecasting**  

## 🚀 **Project Overview**  
In the ever-evolving world of social media, **influence is currency.** But how do we differentiate **genuine engagement from manipulation**? How can brands **predict influencer growth and audience loyalty**?  

This project leverages **SQL, data science, and machine learning** to analyze Instagram influencer behavior, detect anomalies (e.g., fake engagement, bot activity), and forecast **influence growth trends**—critical insights for e-commerce brands, advertisers, and social media platforms like **Meta (Instagram & Facebook).**  

---

## 🎯 **Key Objectives**  
✅ **Anomaly Detection:** Identifying fake engagement, bot-driven activity, and suspicious patterns  
✅ **Growth & Engagement Forecasting:** Predicting follower trends and influencer impact  
✅ **Market Insights:** Evaluating the **ROI of influencer partnerships**  
✅ **Data-Driven Decision Making:** Providing actionable insights for brand collaborations  

---

## 📊 **Dataset Overview**  
This study analyzes **top Instagram influencers**, extracting:  
- **Follower Growth:** Tracking audience trends  
- **Engagement Metrics:** Likes, comments, shares, and total influence score  
- **Anomaly Indicators:** Unusual spikes, bot-driven engagement, and sudden audience drops  
- **Influencer Classification:** Categorizing influencers based on reach & authenticity  

---

## 🔍 **SQL-Driven Insights**  
This project starts with **SQL queries** to extract, clean, and analyze data.  

✅ **Example Query: Detecting Influencers with Suspicious Engagement Rates**  
```sql
SELECT influencer_name, followers, engagement_rate, avg_likes, total_likes
FROM instagram_data
WHERE engagement_rate > 50 OR engagement_rate < 1
ORDER BY engagement_rate DESC;
```
💡 **Findings:**  
✔ **Some influencers have engagement rates above 50%—a potential red flag for fake activity.**  
✔ **Accounts with massive followers but low engagement indicate bot-driven follower inflation.**  

---

## 🚀 **Anomaly Detection: Spotting Fake Engagement & Bot Activity**  
💡 **Why is Anomaly Detection Important?**  
Instagram is flooded with **fake followers and bot-driven likes**—distorting marketing investments.  
This study applies **unsupervised learning techniques** to flag **suspicious influencer behavior.**  

### 📌 **Key Anomalies Detected:**  
📍 **Fake Engagement:** Unnaturally high like-to-follower ratios suggest **purchased likes.**  
📍 **Bot Activity:** Accounts with low comment diversity but high engagement.  
📍 **Follower-Engagement Mismatch:** High followers but **low average likes = ghost followers.**  
📍 **Rapid Engagement Drops:** Sudden audience decline → Possible **shadowban or lost credibility.**  

✅ **Example Approach: Isolation Forest for Anomaly Detection**  
```python
from sklearn.ensemble import IsolationForest

model = IsolationForest(contamination=0.05)  # Flagging top 5% anomalies
df["anomaly_score"] = model.fit_predict(df[["followers", "engagement_rate", "avg_likes"]])
df[df["anomaly_score"] == -1]  # Outlier detection
```
🔹 **Result:** Accounts with artificially inflated engagement flagged as anomalies.  

---

## 📈 **Influence Growth & Engagement Prediction**  
💡 **Why Predict Influencer Growth?**  
Brands & marketers **invest heavily in influencers**—but how do they know who will remain **relevant**?  
This study builds a **time-series model** to predict **influencer growth trends**.  

✅ **Example Approach: Facebook Prophet for Time-Series Forecasting**  
```python
from fbprophet import Prophet

model = Prophet()
df_train = df[['date', 'followers']].rename(columns={'date': 'ds', 'followers': 'y'})
model.fit(df_train)
future = model.make_future_dataframe(periods=90)  # Predicting next 3 months
forecast = model.predict(future)
```
🔹 **Result:** Predicts audience growth for **data-driven marketing decisions.**  

✅ **Key Takeaways:**  
✔ **Verified accounts have more stable engagement trends.**  
✔ **High engagement volatility suggests possible audience manipulation.**  
✔ **Consistent engagement growth → More reliable influencers for brand partnerships.**  

---

## 📊 **Data Visualization & Insights**  
📌 **Heatmaps** – Analyzing correlation between followers, engagement, and authenticity  
📌 **Trend Analysis** – Forecasting follower & engagement growth  
📌 **Cluster Analysis** – Identifying different influencer types (nano, micro, macro, mega)  

✅ **Example: Engagement vs. Followers Scatter Plot**  
```python
import seaborn as sns
import matplotlib.pyplot as plt

sns.scatterplot(x=df["followers"], y=df["engagement_rate"], hue=df["anomaly_score"])
plt.title("Engagement vs. Followers (Anomaly Detection)")
plt.show()
```

---

## 🎯 **Why This Project Stands Out for Meta's Data Science Team**  
This project **aligns with Meta’s Data Scientist role** by demonstrating:  
✔ **Advanced SQL & Python expertise** for data-driven insights  
✔ **Product Analytics Mindset** – Understanding user behavior & engagement patterns  
✔ **Machine Learning for Anomaly Detection & Forecasting**  
✔ **Data-Driven Storytelling** – Turning insights into strategic decisions  

---

## 🔮 **Future Scope**  
🔹 **Real-time influencer monitoring system using Meta API**  
🔹 **Automated fraud detection & influencer classification**  
🔹 **Building an ETL pipeline for influencer analytics**  

---

## 🛠 **How to Run This Project**  
1. Clone the repo:  
   ```bash
   git clone https://github.com/shrunalisalian/instagram-influencer-analysis.git
   ```
2. Install dependencies:  
   ```bash
   pip install -r requirements.txt
   ```
3. Run the Jupyter Notebook:  
   ```bash
   jupyter notebook instagram-case-study.ipynb
   ```

---

## 📌 **Connect with Me**  
- **LinkedIn:** [Shrunali Salian](https://www.linkedin.com/in/shrunali-salian/)  
- **Portfolio:** [Your Portfolio Link](#)  
- **Email:** [Your Email](#)  

---

### 🚀 **Final Thoughts**  
This project **goes beyond basic analytics**—it provides **real-world insights** into Instagram’s influence economy. **Anomaly detection, engagement forecasting, and SQL-driven insights** make this study a **powerful tool for e-commerce brands, digital marketers, and Meta’s data science team.**  
