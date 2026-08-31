# Customer Churn Prediction & Customer Behavior Analysis

> End-to-end Data Science Portfolio Project

## Overview

Project ini bertujuan untuk menganalisis perilaku pelanggan dan membangun model Machine Learning untuk memprediksi pelanggan yang berpotensi mengalami churn.

Analisis dilakukan dengan menggabungkan data customer profile, transaction history, dan customer interactions untuk menghasilkan customer-level features yang dapat digunakan dalam proses analisis dan prediksi churn.

Project ini mencakup proses data validation, data cleaning, exploratory data analysis, data integration, feature engineering, machine learning modeling, model evaluation, feature importance, hingga business insights dan customer retention recommendations.

## Business Questions

- Bagaimana karakteristik pelanggan yang mengalami churn?
- Apakah aktivitas transaksi berhubungan dengan customer churn?
- Apakah tingkat engagement pelanggan berhubungan dengan customer churn?
- Faktor apa saja yang paling berkontribusi terhadap prediksi churn?
- Seberapa baik Machine Learning dapat memprediksi pelanggan yang berisiko churn?
- Bagaimana hasil prediksi dapat digunakan untuk mendukung strategi customer retention?

## Project Objective

- Melakukan data validation dan data cleaning pada beberapa sumber data pelanggan.
- Menggabungkan data customer profile, transaksi, dan interaksi pelanggan.
- Melakukan exploratory data analysis untuk memahami pola perilaku pelanggan.
- Membuat behavioral features pada tingkat pelanggan.
- Menganalisis hubungan antara aktivitas transaksi, engagement, dan churn.
- Membandingkan beberapa algoritma Machine Learning.
- Mengevaluasi performa model menggunakan Accuracy, Precision, Recall, F1-Score, dan ROC-AUC.
- Mengidentifikasi fitur yang paling berpengaruh terhadap prediksi churn.
- Menghasilkan business insights dan rekomendasi untuk mendukung customer retention.

## Dataset

Dataset yang digunakan adalah **CRROS Customer Behavior Dataset** dari Hugging Face.

Dataset terdiri dari beberapa sumber data:

| File | Deskripsi |
| --- | --- |
| `customers.csv` | Informasi profil pelanggan |
| `products.csv` | Informasi produk |
| `transactions.csv` | Riwayat transaksi pelanggan |
| `interactions.csv` | Aktivitas dan interaksi pelanggan |

Data yang digunakan dalam proses analisis:

- Customers: 8,000 rows × 7 columns
- Products: 120 rows × 5 columns
- Transactions: 24,431 rows × 7 columns
- Interactions: 250,000 rows × 6 columns

Data mentah kemudian diproses dan digabungkan menjadi dataset pada tingkat pelanggan untuk kebutuhan analisis dan Machine Learning.

## Project Workflow

```text
Business Problem
       ↓
Data Understanding
       ↓
Data Validation
       ↓
Data Cleaning
       ↓
Exploratory Data Analysis
       ↓
Data Integration
       ↓
Feature Engineering
       ↓
Model Preparation
       ↓
Machine Learning
       ↓
Model Comparison
       ↓
Final Model Evaluation
       ↓
Feature Importance
       ↓
Business Insights
       ↓
Customer Retention Recommendations
Feature Engineering

Feature engineering dilakukan untuk mengubah data transaksi dan interaksi menjadi informasi yang lebih relevan pada tingkat pelanggan.

Customer Profile
Age
Gender
Customer Segment
Location
Acquisition Channel
Transaction Behavior
Total Transactions
Total Spending
Average Transaction Value
Purchase Frequency
Unique Products
Engagement Behavior
Total Interactions
Marketing Interactions
Engagement Frequency
Interaction Types Count
Recency / Activity
Days Since Last Purchase
Days Since Last Interaction

Feature tersebut kemudian digunakan untuk membentuk dataset final yang menjadi input untuk proses Machine Learning.

Machine Learning Models

Tiga algoritma Machine Learning dibandingkan dalam project ini:

Logistic Regression — digunakan sebagai baseline model.
Decision Tree — digunakan untuk melihat pola keputusan yang lebih interpretable.
Random Forest — digunakan sebagai ensemble model untuk memperoleh performa prediksi yang lebih robust.

Model dievaluasi menggunakan:

Accuracy
Precision
Recall
F1-Score
ROC-AUC

Untuk kasus churn, Recall dan F1-Score menjadi metrik penting karena model diharapkan dapat mendeteksi pelanggan yang berpotensi churn.

Model Comparison
Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC
Random Forest	0.985	1.000	0.900	0.947	0.978
Logistic Regression	0.959	0.844	0.900	0.871	0.966
Decision Tree	0.907	0.643	0.900	0.750	0.944

Berdasarkan hasil perbandingan, Random Forest dipilih sebagai final model karena memberikan performa keseluruhan terbaik dengan Accuracy 98.5%, Precision 100%, F1-Score 94.7%, dan ROC-AUC 0.978.

Final Model Performance

Final Model: Random Forest

Metric	Score
Accuracy	98.5%
Precision	100.0%
Recall	90.0%
F1-Score	94.7%
ROC-AUC	0.978

Hasil evaluasi menunjukkan bahwa model mampu mengklasifikasikan customer churn dengan performa yang sangat baik pada data pengujian.

Model menghasilkan Recall sebesar 90%, yang berarti sebagian besar pelanggan yang benar-benar churn berhasil teridentifikasi oleh model.

Feature Importance

Berdasarkan Random Forest, fitur dengan kontribusi terbesar terhadap prediksi churn adalah:

Rank	Feature	Importance
1	Customer Segment - Low	0.183388
2	Days Since Last Interaction	0.104594
3	Days Since Last Purchase	0.095600
4	Purchase Frequency	0.088023
5	Unique Products	0.072949
6	Total Transactions	0.065895
7	Total Spending	0.065509
8	Total Interactions	0.055064
9	Engagement Frequency	0.054639
10	Marketing Interactions	0.051510

Hasil tersebut menunjukkan bahwa karakteristik customer segment dan pola aktivitas pelanggan, terutama recency transaksi, recency interaksi, serta frekuensi pembelian, menjadi fitur yang penting dalam prediksi churn.

Catatan: feature importance menunjukkan kontribusi relatif fitur terhadap prediksi model dan tidak secara langsung membuktikan hubungan sebab-akibat.

Key Business Insights

Berdasarkan hasil analisis:

Overall churn rate sebesar 15.31%, sehingga terdapat sebagian pelanggan yang perlu mendapatkan perhatian dalam strategi retention.
Customer segment low memiliki churn rate tertinggi sebesar 93.53% berdasarkan hasil pengelompokan customer segment.
Pelanggan pada purchase frequency group Low memiliki churn rate sebesar 70.48%, menunjukkan bahwa rendahnya frekuensi pembelian berkaitan dengan tingkat churn yang lebih tinggi.
Pelanggan pada engagement group Low memiliki churn rate sebesar 78.64%, menunjukkan adanya hubungan antara rendahnya aktivitas engagement dan churn.
Pelanggan yang churn memiliki rata-rata aktivitas transaksi dan engagement yang jauh lebih rendah dibandingkan pelanggan yang tidak churn. Rata-rata total transaksi pelanggan churn adalah 2.91, dibandingkan 23.46 pada pelanggan yang tidak churn.
Rata-rata total spending pelanggan churn adalah 48,037.83, sedangkan pelanggan yang tidak churn memiliki rata-rata total spending sebesar 418,452.85.
Rata-rata total interactions pelanggan churn adalah 40.03, sedangkan pelanggan yang tidak churn mencapai 235.85.
Feature importance Random Forest menunjukkan bahwa customer segment, days since last interaction, days since last purchase, dan purchase frequency merupakan beberapa fitur dengan kontribusi terbesar dalam prediksi churn.
Customer Retention Recommendations

Berdasarkan hasil analisis dan prediksi model, beberapa rekomendasi yang dapat diterapkan adalah:

Prioritaskan pelanggan dengan probabilitas churn tinggi dari hasil prediksi model untuk mendapatkan tindakan retention lebih awal.
Monitor pelanggan dengan aktivitas pembelian yang menurun, terutama pelanggan dengan purchase frequency rendah.
Monitor pelanggan dengan engagement rendah, khususnya pelanggan yang memiliki sedikit interaksi dan sudah lama tidak melakukan aktivitas.
Gunakan customer segment dan behavioral patterns untuk membuat strategi retention yang lebih terarah dan relevan.
Gunakan hasil churn prediction sebagai alat prioritas, bukan sebagai kepastian bahwa pelanggan akan benar-benar churn.
Prediction Output

Model menghasilkan output prediksi pelanggan yang berisi:

Customer ID
Actual Churn
Churn Prediction
Prediction Label
Churn Probability

Contoh hasil prediksi:

Customer ID	Actual Churn	Prediction	Label	Churn Probability
C00708	1	1	Churn	100.00%
C00971	1	1	Churn	99.67%
C00600	1	1	Churn	99.33%
C00401	1	1	Churn	99.00%
C00023	1	1	Churn	99.00%

Output tersebut dapat digunakan sebagai dasar untuk membuat daftar prioritas pelanggan yang perlu mendapatkan perhatian dari tim customer retention.

Project Output

Project menghasilkan beberapa output utama:

Processed Data

data/processed/customer_features_FINAL.csv

Dataset customer-level hasil feature engineering yang digunakan dalam proses analisis dan modeling.

Prediction Output

data/processed/customer_churn_predictions_FINAL.csv

File berisi hasil prediksi churn dan probabilitas churn setiap customer pada data pengujian.

Final Model

models/best_churn_FINAL.pkl

File model Machine Learning terbaik yang digunakan untuk menghasilkan prediksi churn.

Visualizations

Project juga menghasilkan visualisasi untuk mendukung:

Churn distribution
Customer behavior analysis
Transaction behavior analysis
Engagement analysis
Feature importance
Model evaluation
Project Structure
customer-churn-prediction/

├── data/
│   ├── raw/
│   │   ├── customers.csv
│   │   ├── products.csv
│   │   ├── transactions.csv
│   │   └── interactions.csv
│   │
│   └── processed/
│       ├── customer_features_FINAL.csv
│       └── customer_churn_predictions_FINAL.csv
│
├── models/
│   └── best_churn_FINAL.pkl
│
├── notebooks/
│   └── customer_churn_analysis.ipynb
│
├── images/
│   └── [visualization files]
│
├── .gitignore
└── README.md
Tech Stack
Tool	Fungsi
Python	Programming dan data analysis
Pandas	Data manipulation dan preprocessing
NumPy	Numerical computation
Matplotlib	Data visualization
Seaborn	Statistical data visualization
Scikit-learn	Machine Learning dan model evaluation
Jupyter Notebook	Development dan dokumentasi analisis
Anaconda	Python environment
Git & GitHub	Version control dan portfolio
Conclusion

Project ini menunjukkan proses end-to-end dalam membangun solusi Machine Learning untuk customer churn, mulai dari memahami data, melakukan validation dan cleaning, mengintegrasikan beberapa sumber data, melakukan feature engineering, hingga membangun dan mengevaluasi model.

Dari tiga model yang dibandingkan, Random Forest menjadi final model dengan performa terbaik, dengan Accuracy sebesar 98.5%, F1-Score sebesar 94.7%, dan ROC-AUC sebesar 0.978 pada data pengujian.

Hasil analisis juga menunjukkan bahwa pola aktivitas pelanggan seperti recency interaksi, recency pembelian, purchase frequency, jumlah transaksi, spending, dan engagement memiliki kontribusi penting dalam proses prediksi churn.

Dengan demikian, model dapat digunakan sebagai alat pendukung untuk memprioritaskan pelanggan yang memiliki risiko churn tinggi, sehingga perusahaan dapat melakukan tindakan customer retention secara lebih terarah.

Author

Dina Kartika Pramudita

Data Science | Data Analyst | Machine Learning
