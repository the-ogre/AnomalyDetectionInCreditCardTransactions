# Anomaly Detection in Credit Card Transactions

## Abstract
The global financial landscape faces a significant challenge with credit card fraud, which reached approximately $27.85 billion in losses worldwide in 2018. This project explores the application of machine learning techniques, specifically Autoencoders, for fraud detection in credit card transactions. The primary objective is to investigate whether Autoencoders outperform Random Forest models in terms of the Area Under the Receiver Operating Characteristic Curve (AUROC) score. Three different models were developed, including Random Forest, a vanilla Autoencoder, and a Long Short-Term Memory (LSTM) Autoencoder. These models were trained on two distinct datasets, one comprising real-life data and the other synthetic data. In addition, the LSTM Autoencoder was trained in two different ways: one with data sorted by time and another with data sorted by users. A third model was subsequently created by combining the outputs of the two LSTM Autoencoder models. The models' performance was evaluated based on accuracy, recall, and AUROC, with AUROC being the primary metric.

## 1. Introduction
Credit card fraud is a critical issue affecting financial institutions and individuals globally. Detecting fraudulent transactions is essential to mitigate losses and maintain trust in financial systems. Machine learning techniques, particularly Autoencoders, hold promise for improving fraud detection. This project aims to assess whether Autoencoders can outperform Random Forest models in identifying fraudulent credit card transactions.

## 2. Methodology
### 2.1 Data
Two distinct datasets were used for model training and evaluation. The first dataset consisted of real-life credit card transaction data, while the second dataset was synthetic data generated for experimentation.

### 2.2 Models
Three models were developed for this study:
- **Random Forest Model:** This model serves as a benchmark for fraud detection.
- **Vanilla Autoencoder Model:** A standard Autoencoder architecture used for anomaly detection.
- **LSTM Autoencoder Model:** A variant of Autoencoder using Long Short-Term Memory cells for capturing temporal dependencies in credit card transactions.

### 2.3 Model Training
The LSTM Autoencoder model was trained in two different ways on the synthetic dataset:
- Sorting data by time.
- Sorting data by users.
A hybrid LSTM Autoencoder model was created by combining the outputs of the two LSTM Autoencoder models.

### 2.4 Evaluation Metrics
The models were evaluated using the following metrics:

- **Accuracy:** Accuracy measures the overall correctness of the model's predictions. While important, it may not be the most suitable metric for imbalanced datasets as it can be skewed by the dominant class. We used accuracy to ensure the model performs well on both classes.

- **Recall:** Recall, also known as true positive rate or sensitivity, is a critical metric in credit card fraud detection. It measures the model's ability to detect fraudulent transactions correctly. Given the severe consequences of missing fraudulent cases, optimizing for high recall is essential.

- **AUROC (Area Under the Receiver Operating Characteristic Curve):** AUROC is a standard metric for binary classification tasks like fraud detection. It provides a comprehensive measure of a model's ability to distinguish between the two classes across different probability thresholds. A higher AUROC score indicates better model performance in distinguishing between genuine and fraudulent transactions.

### 2.5 Handling Imbalanced Datasets (Extended)
Imbalanced datasets pose a significant challenge in credit card fraud detection. In addition to the techniques mentioned earlier, we explored several other methods to enhance our model's ability to detect fraudulent transactions:

- **Cost-sensitive Learning:** By assigning different misclassification costs to each class (fraudulent and non-fraudulent), we guided the model to prioritize minimizing the cost associated with misclassifying fraudulent transactions. This technique is particularly useful when the consequences of missing fraudulent cases are severe.

- **Ensemble Methods:** We investigated ensemble techniques such as Random Undersampling Boosting (RUSBoost) and EasyEnsemble, which combine multiple classifiers to improve overall model performance. These methods often work well with imbalanced datasets as they focus on the minority class.

- **Threshold Adjustment:** Fine-tuning the decision threshold of the model can be an effective way to balance precision and recall. By adjusting the threshold, we aimed to increase the number of detected fraudulent cases while controlling false positives.

- **Anomaly Detection Algorithms:** In addition to traditional classification models, we considered using anomaly detection algorithms such as Isolation Forest and One-Class SVM. These algorithms are well-suited for identifying rare events, making them valuable for detecting credit card fraud.

- **Data Augmentation:** Data augmentation techniques, typically used in computer vision, were explored to increase the diversity of the minority class. This involved creating variations of existing fraudulent transactions to enrich the dataset.

- **Sequential Models:** Given the temporal nature of credit card transactions, we experimented with sequential models like Recurrent Neural Networks (RNNs) and Gated Recurrent Units (GRUs) to capture time-dependent patterns in the data more effectively.

By incorporating these additional methods into our approach, we aimed to create a robust fraud detection system that excels in handling imbalanced datasets, ultimately enhancing the security and trust in financial transactions.

## 3. Results
The following results were obtained from model evaluation:
- On the real-life dataset, all models had fairly similar AUROC scores, with the Random Forest model achieving the highest AUROC score of 0.9258.
- On the synthetic dataset, the Random Forest model outperformed the Autoencoder models, achieving an AUROC score of 0.8508, while the Autoencoder models obtained lower AUROC scores ranging from 0.6447 to 0.7921.

## 4. Discussion
The results indicate that while the Autoencoders developed in this thesis can be used for anomaly detection in credit card transaction data, their performance varies depending on the dataset. On the real-life dataset, the performance of Autoencoders was competitive with the Random Forest model. However, on the synthetic dataset, the Random Forest model outperformed the Autoencoders in terms of AUROC score.

## 5. Conclusion
In conclusion, this project explored the application of machine learning models, including Autoencoders and Random Forest, for credit card fraud detection. While Autoencoders show promise in detecting anomalies in real-life credit card transaction data, the Random Forest model outperforms them on synthetic data. The choice of model should be tailored to the specific dataset and use case. Future work could focus on optimizing Autoencoder architectures and exploring ensemble techniques to improve performance further.

## 6. Acknowledgments
We would like to express our gratitude to [Your Advisor's Name] for their invaluable guidance and support throughout this research project.

## 7. References
1. Venelin Valkov, "Credit Card Fraud Detection using Autoencoders in Keras," [Medium](https://venelinvalkov.medium.com/credit-card-fraud-detection-using-autoencoders-in-keras-tensorflow-for-hackers-part-vii-20e0c85301bd).
2. [Your Second Reference](https://www.diva-portal.org/smash/get/diva2:1466914/FULLTEXT01.pdf).
3. [Your Third Reference](https://towardsdatascience.com/applying-anomaly-detection-with-autoencoders-to-fraud-detection-feaaee6b5b09).

This project report summarizes the investigation into the use of Autoencoders and Random Forest for credit card fraud detection. The findings suggest that while Autoencoders are a viable option for this task, their performance may vary depending on the nature of the dataset. Further research and optimization are necessary to enhance the effectiveness of these models in real-world financial security applications.
