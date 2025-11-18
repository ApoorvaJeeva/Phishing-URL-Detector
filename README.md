This project is a machine-learning-based phishing-detection system that analyzes URLs/content to predict whether they are safe or malicious.

1. Dataset
Two datasets were used:
PhiUSIIL Phishing URL Dataset: https://archive.ics.uci.edu/dataset/967/phiusiil+phishing+url+dataset
Phishing_site_urls.csv (raw URLs): https://www.kaggle.com/datasets/taruntiwarihp/phishing-site-urls
Final dataset: ~742,000 samples, balanced classes.

2. Data Preprocessing
Standardized labels (1 = Phishing, 0 = Legitimate)
Extracted 22 lexical and statistical features
Cleaned duplicates and missing data
Tokenized URLs at the character level for CNN input

3. Feature Engineering
Numerical features: URL length, special characters, digit ratios, domain info, etc.
Text feature: Full raw URL string

4. Model Architecture
A hybrid approach:
CNN → learns patterns from raw URL text
MLP → learns from handcrafted numerical features
Features concatenated before the final classification layer

5. Training
Loss: binary_crossentropy
Optimizer: Adam
Early stopping to reduce overfitting
Class weights for balance

6. Results
Metric	   Phishing	   Legitimate
Precision	 96.70%     	98.39%
Recall	   96.81%	      98.33%
F1-Score	 96.75%	      98.36%

Overall Accuracy: 97.82%

7. Key Observations
The model generalizes well with minimal overfitting
Outperforms traditional ML models
Hybrid architecture effectively captures structural + lexical URL patterns

8. References
Phishing datasets from Kaggle and UCI Machine Learning.
