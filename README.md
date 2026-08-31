# Customer Churn Prediction & Customer Behavior Analysis

> End-to-end Data Science Portfolio Project

## Overview

Project ini bertujuan untuk menganalisis perilaku pelanggan dan membangun model Machine Learning untuk memprediksi pelanggan yang berpotensi mengalami churn.

Analisis dilakukan dengan menggabungkan data customer profile, transaction history, dan customer interactions untuk menghasilkan customer-level features yang digunakan dalam proses analisis dan prediksi churn.

Project ini mencakup proses data validation, data cleaning, exploratory data analysis, data integration, feature engineering, machine learning modeling, model evaluation, feature importance, business insights, hingga customer retention recommendations.

---

## Business Problem

Perusahaan perlu mengidentifikasi pelanggan yang memiliki risiko churn agar dapat melakukan tindakan retensi lebih awal.

Project ini menjawab beberapa pertanyaan bisnis:

- Karakteristik seperti apa yang dimiliki pelanggan yang churn?
- Apakah aktivitas transaksi berhubungan dengan churn?
- Apakah tingkat engagement berhubungan dengan churn?
- Faktor apa yang paling berpengaruh terhadap churn?
- Seberapa baik Machine Learning dapat memprediksi pelanggan yang berisiko churn?

---

## Project Objective

Tujuan utama project ini adalah:

> Membangun model Machine Learning untuk memprediksi kemungkinan customer churn berdasarkan data customer profile, transaksi, dan customer engagement.

Tujuan tambahan:

- Melakukan data validation dan data cleaning.
- Melakukan exploratory data analysis.
- Menggabungkan beberapa sumber data pelanggan.
- Membuat behavioral features pada level pelanggan.
- Mengidentifikasi karakteristik pelanggan yang berhubungan dengan churn.
- Membandingkan beberapa algoritma Machine Learning.
- Mengevaluasi performa model menggunakan beberapa metrik.
- Mengidentifikasi feature importance.
- Menghasilkan business insights.
- Menyusun rekomendasi customer retention berdasarkan hasil analisis.

---

## Dataset

Project ini menggunakan CRROS Customer Behavior Dataset yang terdiri dari beberapa sumber data:

- `customers.csv` — informasi profil pelanggan.
- `products.csv` — informasi produk.
- `transactions.csv` — riwayat transaksi pelanggan.
- `interactions.csv` — aktivitas interaksi pelanggan.

Data mentah yang digunakan dalam project terdiri dari:

| Dataset | Rows | Columns |
|---|---:|---:|
| Customers | 8,000 | 7 |
| Products | 120 | 5 |
| Transactions | 24,431 | 7 |
| Interactions | 250,000 | 6 |

Data tersebut kemudian diproses dan digabungkan menjadi customer-level dataset untuk kebutuhan analisis dan Machine Learning.

---

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
Model Evaluation
       ↓
Feature Importance
       ↓
Business Insights
       ↓
Customer Retention Recommendations
Data Processing

Beberapa tahapan pengolahan data yang dilakukan:

Memahami struktur masing-masing dataset.
Melakukan pengecekan kualitas data.
Melakukan data validation.
Menangani data sesuai kebutuhan preprocessing.
Mengubah data transaksi dan interaksi menjadi customer-level features.
Menggabungkan customer profile, transaction behavior, dan engagement behavior.
Menyiapkan dataset final untuk proses Machine Learning.
Feature Engineering

Feature engineering dilakukan untuk mengubah data transaksi dan interaksi menjadi informasi perilaku pelanggan.

Customer Profile

Fitur yang digunakan antara lain:

age
gender
customer_segment
location
acquisition_channel
Transaction Behavior

Beberapa behavioral features yang digunakan:

total_transactions
total_spending
average_transaction_value
purchase_frequency
unique_products
Engagement Behavior

Fitur engagement yang digunakan antara lain:

total_interactions
marketing_interactions
engagement_frequency
interaction_types_count
Recency / Activity

Fitur aktivitas pelanggan yang digunakan antara lain:

days_since_last_purchase
days_since_last_interaction

Feature engineering dilakukan pada level pelanggan sehingga setiap customer memiliki representasi perilaku yang dapat digunakan untuk analisis dan prediksi churn.

Machine Learning

Project ini membandingkan tiga algoritma Machine Learning:

1. Logistic Regression

Digunakan sebagai baseline model untuk melihat performa model klasifikasi linear.

2. Decision Tree

Digunakan untuk melihat pola keputusan dan hubungan antar fitur dalam proses klasifikasi.

3. Random Forest

Digunakan sebagai ensemble model untuk memperoleh performa prediksi yang lebih robust.

Model Evaluation

Model dibandingkan menggunakan:

Accuracy
Precision
Recall
F1-Score
ROC-AUC

Untuk kasus customer churn, Recall dan F1-Score menjadi metrik penting karena model diharapkan dapat mendeteksi pelanggan yang berisiko churn.

Model Comparison
Model	Accuracy	Precision	Recall	F1-Score	ROC-AUC
Random Forest	0.985	1.000	0.900	0.947	0.978
Logistic Regression	0.959	0.844	0.900	0.871	0.966
Decision Tree	0.907	0.643	0.900	0.750	0.944
Best Model

Random Forest dipilih sebagai final model karena memberikan performa terbaik berdasarkan hasil perbandingan model.

Final model menghasilkan:

Metric	Score
Accuracy	0.985
Precision	1.000
Recall	0.900
F1-Score	0.947
ROC-AUC	0.978
Feature Importance

Feature importance dari Random Forest digunakan untuk melihat fitur yang paling berkontribusi terhadap hasil prediksi.

Top 10 Features
Rank	Feature	Importance
1	customer_segment_low	0.183388
2	days_since_last_interaction	0.104594
3	days_since_last_purchase	0.095600
4	purchase_frequency	0.088023
5	unique_products	0.072949
6	total_transactions	0.065895
7	total_spending	0.065509
8	total_interactions	0.055064
9	engagement_frequency	0.054639
10	marketing_interactions	0.051510

Hasil feature importance menunjukkan bahwa karakteristik customer_segment_low, aktivitas terakhir pelanggan, dan pola pembelian menjadi beberapa fitur dengan kontribusi terbesar dalam model Random Forest.

Business Insights

Berdasarkan hasil analisis data:

1. Overall Churn Rate

Overall churn rate pada customer-level dataset adalah:

15.31%

Artinya, sebagian pelanggan dalam dataset dikategorikan sebagai pelanggan yang mengalami churn.

2. Customer Segment

Customer segment low memiliki churn rate tertinggi, yaitu:

93.53%

Hasil ini menunjukkan adanya perbedaan yang sangat besar pada tingkat churn berdasarkan customer segment.

3. Purchase Frequency

Kelompok purchase frequency Low memiliki churn rate tertinggi:

70.48%

Hal ini menunjukkan bahwa pelanggan dengan aktivitas pembelian yang rendah memiliki tingkat churn yang lebih tinggi dalam dataset.

4. Customer Engagement

Kelompok engagement Low memiliki churn rate tertinggi:

78.64%

Pelanggan dengan tingkat engagement yang rendah menunjukkan risiko churn yang lebih tinggi dibandingkan kelompok engagement lainnya.

5. Perbedaan Aktivitas Pelanggan

Hasil perbandingan rata-rata behavioral features menunjukkan:

Feature	No Churn	Churn
Total Interactions	235.85	40.03
Marketing Interactions	23.47	3.80
Engagement Frequency	0.33	0.06

Pelanggan yang mengalami churn memiliki rata-rata aktivitas interaksi dan engagement yang lebih rendah dibandingkan pelanggan yang tidak churn.

Customer Churn Prediction

Final Random Forest model digunakan untuk menghasilkan prediksi churn dan probabilitas churn untuk customer pada data pengujian.

Output prediksi terdiri dari:

customer_id
actual
churn_prediction
prediction_label
churn_probability

Contoh hasil prediksi:

Customer ID	Actual	Prediction	Prediction Label	Churn Probability
C00708	1	1	Churn	1.000000
C00971	1	1	Churn	0.996667
C00600	1	1	Churn	0.993333
C00401	1	1	Churn	0.990000
C00023	1	1	Churn	0.990000

Model menghasilkan probabilitas churn yang dapat digunakan sebagai dasar untuk memprioritaskan pelanggan yang membutuhkan perhatian lebih lanjut.

Business Recommendations

Berdasarkan hasil analisis dan model:

1. Prioritaskan Pelanggan Berisiko Tinggi

Pelanggan yang memiliki probabilitas churn tinggi dapat diprioritaskan untuk aktivitas customer retention.

2. Monitor Penurunan Aktivitas Pembelian

Perusahaan dapat memonitor pelanggan dengan aktivitas pembelian dan purchase frequency yang rendah.

3. Tingkatkan Customer Engagement

Pelanggan dengan tingkat interaksi dan engagement rendah dapat menjadi target untuk komunikasi dan retention campaign yang lebih relevan.

4. Gunakan Customer Segment dan Behavioral Pattern

Strategi retention dapat disesuaikan berdasarkan customer segment serta pola transaksi dan engagement pelanggan.

5. Gunakan Prediction sebagai Prioritas Retention

Hasil prediksi churn sebaiknya digunakan sebagai alat untuk menentukan prioritas aktivitas retention, bukan sebagai kepastian bahwa pelanggan akan benar-benar churn.

Project Output

Project menghasilkan beberapa output utama:

data/
├── raw/
│   ├── customers.csv
│   ├── products.csv
│   ├── transactions.csv
│   └── interactions.csv
│
└── processed/
    ├── customer_features_FINAL.csv
    └── customer_churn_predictions_FINAL.csv

images/
    └── visualization outputs

models/
    └── best_churn_FINAL.pkl

notebooks/
    └── customer_churn_analysis.ipynb

.gitignore
requirements.txt
README.md
Final Files

Customer Features

data/processed/customer_features_FINAL.csv

Berisi customer-level features yang telah diproses dan digunakan dalam analisis.

Prediction Output

data/processed/customer_churn_predictions_FINAL.csv

Berisi hasil prediksi churn dan probabilitas churn pelanggan.

Final Model

models/best_churn_FINAL.pkl

Berisi model Random Forest yang dipilih sebagai final model.

Notebook

notebooks/customer_churn_analysis.ipynb

Berisi keseluruhan proses project mulai dari data understanding hingga business recommendations.

Visualization

Project menghasilkan visualisasi untuk mendukung proses analisis, antara lain:

Churn distribution
Customer segment vs churn
Transaction behavior vs churn
Engagement behavior vs churn
Feature importance
Confusion matrix
ROC curve

Visualisasi digunakan untuk membantu memahami pola pelanggan dan mengevaluasi performa model.

Tech Stack
Tool	Fungsi
Python	Pemrograman dan analisis data
Anaconda	Environment management
Jupyter Notebook	Data analysis dan modeling
Pandas	Data manipulation
NumPy	Numerical computation
Matplotlib	Data visualization
Seaborn	Statistical visualization
Scikit-learn	Machine Learning
Git	Version control
GitHub	Project repository
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
├── images/
│   └── visualization outputs
│
├── models/
│   └── best_churn_FINAL.pkl
│
├── notebooks/
│   └── customer_churn_analysis.ipynb
│
├── .gitignore
├── requirements.txt
└── README.md
Key Results
Overall churn rate: 15.31%
Best model: Random Forest
Accuracy: 98.5%
Precision: 100.0%
Recall: 90.0%
F1-Score: 94.7%
ROC-AUC: 0.978

Random Forest memberikan performa terbaik dibandingkan Logistic Regression dan Decision Tree pada data pengujian.

Key Takeaways

Beberapa temuan utama dari project:

Customer segment low memiliki churn rate tertinggi dalam dataset.
Kelompok purchase frequency Low memiliki churn rate yang lebih tinggi.
Kelompok engagement Low menunjukkan churn rate yang lebih tinggi.
Pelanggan churn memiliki rata-rata total interactions yang lebih rendah.
Pelanggan churn memiliki rata-rata marketing interactions yang lebih rendah.
customer_segment_low, days_since_last_interaction, dan days_since_last_purchase merupakan tiga fitur dengan importance tertinggi pada model Random Forest.
Model Random Forest dapat digunakan untuk membantu memprioritaskan pelanggan yang memiliki risiko churn tinggi.
Conclusion

Project ini membangun workflow Data Science end-to-end untuk menganalisis customer behavior dan memprediksi customer churn.

Data customer profile, transaction history, dan customer interactions diolah menjadi customer-level features sebelum digunakan dalam proses Machine Learning.

Dari tiga model yang dibandingkan, Random Forest memberikan performa terbaik dengan Accuracy sebesar 98.5%, Precision 100%, Recall 90%, F1-Score 94.7%, dan ROC-AUC 0.978.

Hasil prediksi dan behavioral insights dapat digunakan sebagai dasar untuk membantu perusahaan memprioritaskan pelanggan yang membutuhkan strategi customer retention.

Author

Dina Kartika Pramudita

Data Science | Data Analytics | Machine Learning
