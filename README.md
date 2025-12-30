🛍️ E-Commerce Neural Recommendation System (Olist Brazil)
PythonPandasScikit-LearnLicense

📖 Project Overview
This project demonstrates the application of Machine Learning to solve the "Discovery Problem" in modern e-commerce. Using a real-world dataset of 100,000 orders from Olist (the largest department store in Brazilian marketplaces), I built a recommendation engine that suggests products to users based on their unique purchase history and product attributes.

🛠️ Technical Stack
Component	Technology
Language	Python 3.8+
Data Manipulation	Pandas, NumPy
Preprocessing	Scikit-Learn (MinMaxScaler)
API & Ingestion	Requests (Kaggle API)
Data Source	Olist Brazilian E-Commerce Public Dataset
Methodology	Hybrid Collaborative Filtering
🔄 Data Engineering & ETL Pipeline
Before modeling could begin, a rigorous ETL (Extract, Transform, Load) process was implemented to synchronize nine disparate data files.

Automated Ingestion
Programmatic download and extraction of datasets via the Kaggle API.
Schema Alignment
Merged customer, order, and product datasets using relational keys (customer_id, order_id, product_id).
Anomaly Detection
Identified and removed logical data inconsistencies (e.g., orders delivered before they were purchased or approved).
Feature Scaling
Applied MinMaxScaler to product prices to ensure the model isn't biased by high-value items.
📊 Key Insights from EDA
User Persistence: Identified repeat customers using customer_unique_id, allowing for long-term behavioral tracking.
Data Integrity: Of 99,441 initial orders, approximately 95,088 met the high-quality threshold required for accurate modeling after anomaly removal.
Category Complexity: Handled translation and categorization of products from Portuguese to English for better feature interpretability.
🚀 Recommender Implementation
The system utilizes a custom recommendation function to generate predictions.

The Workflow
def recommend_products(user_id):    # 1. Input: Unique User ID    profile = get_buyer_profile(user_id)        # 2. Logic: Score products against Buyer Profile    #    - Category Affinity    #    - Price Range Compatibility    scores = score_products(profile, all_products)        # 3. Output: Top-10 Recommendations    return scores.sort_values(ascending=False).head(10)
Output: Returns the Top-10 recommended Product IDs tailored to the specific user.

🗺️ Roadmap & Future Enhancements
[ ] Deep Learning Integration
Transition from Matrix Factorization to Neural Collaborative Filtering (NCF) using TensorFlow.
[ ] Model Deployment
Wrap the model in a Flask or FastAPI backend to serve real-time recommendations.
[ ] Evaluation Metrics
Implement metrics like Hit Rate or NDCG (Normalized Discounted Cumulative Gain) to evaluate recommendation precision via A/B Testing.
👨‍💻 Author
Developed by David Owino as part of a Machine Learning MSc in Data Science.

Connect with Me
Portfolio
GitHub
LinkedIn
Twitter