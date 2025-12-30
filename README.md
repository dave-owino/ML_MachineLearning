# E-Commerce Neural Recommendation System (Olist Brazil)

## 1. Project Overview
This project demonstrates the application of Machine Learning to solve the "Discovery Problem" in modern e-commerce. Using a real-world dataset of 100,000 orders from Olist (the largest department store in Brazilian marketplaces), I built a recommendation engine that suggests products to users based on their unique purchase history and product attributes.

## 2. Technical Stack
* **Language:** Python
* **Libraries:** Pandas, NumPy, Scikit-Learn, Requests
* **Model Logic:** Hybrid Collaborative Filtering / Embedding-based Scoring
* **Data Source:** Olist Brazilian E-Commerce Public Dataset

## 3. Data Engineering & ETL Pipeline
Before modeling, a rigorous ETL process was implemented to synchronize nine disparate data files:
1. **Automated Ingestion:** Programmatic download and extraction of datasets via Kaggle API/Requests.
2. **Schema Alignment:** Merged customer, order, and product datasets using relational keys (`customer_id`, `order_id`, `product_id`).
3. **Integrity Engineering:** Developed a custom validation suite to detect anomalies, such as orders delivered before they were approved.
4. **Feature Scaling:** Applied `MinMaxScaler` to product prices to ensure model stability across different price brackets.



## 4. Recommender Implementation
The system utilizes a custom recommendation function:
- **Encoding:** Implemented Label Encoding for high-cardinality data like User IDs and Product IDs.
- **Neural Embeddings:** The logic prepares data for embedding-based scoring to identify category affinity.
- **Ranking:** The model scores all available items for a specific user and returns the Top-10 most relevant products.

## 5. Key Insights
- **Data Integrity:** Out of ~99,000 initial orders, 95,088 met the high-quality threshold required for modeling after programmatic cleaning.
- **User Persistence:** Utilized `customer_unique_id` to track repeat purchase behavior across different order sessions.

## 6. Future Enhancements
- **Deep Learning:** Transition to Neural Collaborative Filtering (NCF) using TensorFlow/Keras.
- **Deployment:** Wrap the model in a FastAPI backend to serve real-time recommendations.