# E-Commerce Customer Segmentation using RFM and K-Means

## Project Objective

The objective of this project is to analyze e-commerce transaction data and segment customers using RFM analysis and K-Means clustering.

This helps businesses:
- Identify high-value customers
- Improve customer retention
- Create personalized marketing strategies
- Detect inactive customers

---

# Dataset Description

The dataset contains transaction-level purchase records from an e-commerce business.

## Columns

| Column | Description |
|---|---|
| InvoiceNo | Invoice number |
| StockCode | Product code |
| Description | Product description |
| Quantity | Quantity purchased |
| InvoiceDate | Purchase date |
| UnitPrice | Product price |
| CustomerID | Unique customer ID |
| Country | Customer country |

Each row represents one purchased product in a transaction.

---

# Data Cleaning

The following cleaning operations were performed:

- Removed missing Customer IDs
- Removed missing descriptions
- Removed cancelled invoices
- Removed duplicate records
- Removed negative quantities
- Removed zero/negative prices
- Converted InvoiceDate into datetime format

Final cleaned dataset shape:
```python
(XXXXX, XX)
```

---

# Feature Engineering

Customer-level features created:

- Total Revenue
- Total Purchases
- Total Quantity Purchased
- Average Order Value
- Unique Products Purchased

## RFM Features

### Recency
Days since customer's last purchase

### Frequency
Total number of purchases

### Monetary
Total customer spending

---

# Exploratory Data Analysis (EDA)

## 1. Countries Generating Highest Revenue

Findings:
- United Kingdom generated the highest revenue
- Germany and France were also major contributors
- Most revenue came from European countries

### Business Insight
The company should focus marketing efforts on high-performing countries.

---

## 2. Most Sold Products

Findings:
- Decorative and gift-related products were frequently purchased
- Certain products had very high order quantities

### Business Insight
Popular products should always remain in inventory.

---

## 3. Highest Revenue Products

Findings:
- Premium-priced items generated the highest revenue
- Some products generated high revenue despite lower quantities

### Business Insight
High-revenue products should receive promotional visibility.

---

## 4. Purchase Frequency Distribution

Findings:
- Most customers made only a few purchases
- A small number of customers purchased very frequently

### Business Insight
Frequent customers represent loyal customer segments.

---

## 5. Order Value Distribution

Findings:
- Most orders had low to medium order value
- Few customers generated extremely large orders

### Business Insight
High spenders should receive loyalty rewards.

---

## 6. Outlier Detection

Findings:
- Significant outliers existed in revenue and quantity
- Some customers spent substantially more than average

### Business Insight
Outliers may represent VIP customers or bulk buyers.

---

# K-Means Clustering

## Clustering Steps

1. Selected RFM features
2. Scaled data using StandardScaler
3. Used Elbow Method
4. Applied K-Means clustering
5. Assigned cluster labels

Optimal clusters selected:
```python
4
```

---

# Cluster Interpretation

| Cluster | Characteristics | Customer Type |
|---|---|---|
| 0 | good frequency, high monetary, moderate recency | Active or valuable customers |
| 1 | high frequency and monetary, good recency | champions or high value Customers |
| 2 | least recency, lowest frequency and monetary value | Lapsed or at risked Customers |
| 3 | Low spending and infrequent purchases | One time buyers |

---

# Business Recommendations
Based on the identified customer clusters, here are strategic recommendations to engage with each segment and maximize their business value:

Cluster 0: Active & Valuable Customers
Customer Behavior: Consistent engagement, good spending, moderate frequency.
Recommendations:
1. Loyalty Programs: Introduce tiered loyalty programs to reward their ongoing activity and encourage them to move towards the 'Champion' segment.
2. Cross-selling & Up-selling: Based on their purchase history, offer complementary products or premium versions of their frequently bought items through personalized recommendations.
3. Engagement: Send exclusive content, early access to sales, or sneak peeks of new products to maintain their interest and make them feel valued.
4. Retention Focus: Implement proactive retention strategies to ensure they don't become 'At-Risk' (e.g., occasional check-ins, satisfaction surveys).

Cluster 1: Champions / High-Value Loyal Customers
Customer Behavior: Most engaged, highest frequency, highest monetary value. Your best customers.
Recommendations:
1. VIP Treatment: Offer exclusive VIP experiences, dedicated customer support, or special recognition (e.g., 'Top Customer' badges).
2. Exclusive Access: Provide early access to new product launches, beta testing opportunities, or members-only events.
3. Referral Programs: Encourage them to refer new customers with generous incentives, as they are your most enthusiastic advocates.
4. Personalized Appreciation: Send personalized thank-you notes, small gifts, or special birthday discounts to deepen their loyalty.
5. Feedback Integration: Actively solicit their feedback for product development or service improvements, making them feel heard and valued.

Cluster 2: Lapsed / At-Risk Customers
Customer Behavior: Low recency, lowest frequency and monetary value. Likely disengaged or churned.
Recommendations:
1. Re-engagement Campaigns: Launch targeted win-back campaigns with compelling offers (e.g., significant discounts on their last purchased item, limited-time promotions).
2. Surveys & Feedback: Send short surveys to understand why they became inactive and gather insights to prevent future churn. Based on feedback, tailor specific solutions.
3. Reminders: Gently remind them of products they previously viewed or items in their abandoned carts. Highlight new arrivals that might pique their interest.
4. Value Proposition Refresh: Reiterate the brand's unique selling points or new features that might draw them back.

Cluster 3: New / One-Time Buyers / Occasional Shoppers
Customer Behavior: Recent purchase, but low frequency and monetary value. Potential for growth.
Recommendations:
1. Onboarding Programs: Implement a structured onboarding series of emails to educate them about product benefits, how-to guides, and encourage a second purchase.
2. Second Purchase Incentives: Offer a special discount or free shipping on their next purchase within a specific timeframe.
3. Personalized Recommendations: Leverage their initial purchase to suggest relevant products and guide them towards items that align with their interests.
4. Educational Content: Provide blog posts, videos, or tutorials related to their purchased items to enhance their product experience and encourage deeper engagement.
5. Nurturing: Focus on building a relationship and showcasing value to convert them into more frequent, loyal customers over time.

---

# Conclusion

This project successfully identified meaningful customer segments using RFM analysis and K-Means clustering.

The analysis can help the business:
- Improve customer retention
- Increase marketing effectiveness
- Identify high-value customers
- Personalize customer experience

---

# Technologies Used

- Python
- Pandas
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn
- Google Colab

---

# Project Structure

```bash
├── Ecommerce_Customer_Segmentation.ipynb
├── README.md
├── requirements.txt
├── dataset_source.md
├── outputs/
└── images/
```

---

# How to Run

1. Clone repository
2. Install dependencies

```bash
pip install -r requirements.txt
```

3. Open google collab notebook
4. Run all cells sequentially
