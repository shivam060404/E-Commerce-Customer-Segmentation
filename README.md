# E-Commerce-Customer-Segmentation
This project automates customer segmentation for personalized marketing in e-commerce using AI techniques. It leverages RFM (Recency, Frequency, Monetary) analysis, advanced clustering, and generative AI to segment customers and generate tailored marketing content. The system supports real-time updates and preserves historical segment data for comparison.

Table of Contents:
-Overview
-Features
-Requirements
-Installation
-Usage
-Project Structure
-Dataset
-Future Improvements
-License

Overview:-
The goal is to segment e-commerce customers into meaningful groups for targeted marketing campaigns. The project uses a combination of traditional machine learning (K-Means clustering) and optional deep learning (autoencoders with PyTorch Lightning), with real-time data updates simulated via pandas. It also integrates the Gemini API for generating personalized marketing emails and preserves old segment data for tracking changes.

Features:
1) RFM Analysis: Calculates Recency, Frequency, and Monetary values from transaction data.
2) Automated Clustering: Uses K-Means to segment customers, with scalability for real-time updates.
3) Explainability: Integrates SHAP for feature importance analysis (optional).
4) Visualization: Generates 3D scatter plots with Plotly.
5) Generative AI: Uses the Gemini API to create personalized marketing emails.
6) Version Control: Saves old segment data before updates for comparison.
7) Real-time Simulation: Handles incoming data and re-clusters dynamically.


Requirements:
-Python 3.8+
-Libraries:
-pandas
-scikit-learn
-pytorch-lightning (optional, for deep learning)
-google-generativeai (for Gemini API)
-plotly
-shap (optional, for explainability)
-sqlite3 (optional, for database storage)
-A Gemini API key from Google Cloud (replace 'your-gemini-api-key' in the code).
-An e-commerce dataset (e.g., UCI Online Retail Dataset).

Installation
Clone the Repository:
git clone https://github.com/shivam060404/E-Commerce-Customer-Segmentation.git
cd E-Commerce-Customer-Segmentation

Install Dependencies:
pip install pandas scikit-learn pytorch-lightning google-generativeai plotly shap

Set Up Gemini API:
Obtain an API key from Google Cloud.
Replace 'your-gemini-api-key' in the code with your actual key.

Download a Dataset:
Use the UCI Online Retail Dataset or your own e-commerce data.
Place it in the data/ folder (e.g., data/Online Retail.xlsx).

Usage:
Run the Main Script:
python main.py
This will load the dataset, perform RFM analysis, cluster customers, and save the results.
New data is simulated, and old segments are preserved in rfm_old.csv.

Generate Marketing Content:
The script uses the Gemini API to create emails based on cluster strategies (e.g., VIP discounts).

View Visualizations:
Open the generated Plotly HTML files (e.g., segments.html) in a browser.

Compare Old and New Segments:
Check rfm_old.csv and updated_customer_segments.csv for differences

Example Output
Updated segments:
CustomerID  Recency  Frequency  Monetary  Cluster  MarketingStrategy
12345       10       2         100       0        VIP Discount
12346       20       3         250       2        Loyalty Reward

Generated email:
Subject: Your Exclusive VIP Offer Awaits!
Dear Valued Customer,
Enjoy 20% off your next purchase with code VIP20!
Shop now,
[Your Company]

Project Structure:
ai-customer-segmentation/
├── data/
│   └── Online Retail.xlsx    # E-commerce dataset
├── main.py                   # Main script for segmentation and updates
├── rfm_old.csv               # Saved old segments
├── updated_customer_segments.csv  # Updated segments
├── requirements.txt          # Dependencies
└── README.md                 # This file

Dataset:
The project uses the UCI Online Retail Dataset by default, which contains:

Columns: InvoiceNo, StockCode, Description, Quantity, InvoiceDate, UnitPrice, CustomerID, Country
Source: UCI Machine Learning Repository
You can replace it with your own dataset, ensuring it has customer transaction data.

Future Improvements
Integrate with Apache Kafka for true real-time streaming.
Deploy as a web app using FastAPI or Flask.
Add automated cluster number optimization (e.g., elbow method).
Enhance with customer demographics or behavioral data.
Implement a feedback loop to evaluate marketing campaign effectiveness.

License
This project is licensed under the MIT License. See the LICENSE file for details.
