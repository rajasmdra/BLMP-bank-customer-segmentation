# Bank Customer Segmentation and Classification

## Project Overview
This project adopts a hybrid machine learning approach to analyze bank customer data. The first phase utilizes unsupervised learning to group customers into distinct segments based on their demographic profiles and transactional behavior. The second phase employs supervised learning to build classification models capable of automatically predicting the segment of new customers. This project aims to assist the bank in designing personalized marketing strategies and improving customer retention.

## Technologies and Libraries Used
This project is built using Python and leverages the following data science libraries:
* **pandas** & **NumPy**: For data loading, structural manipulation, and numerical computations.
* **Matplotlib** & **Seaborn**: For exploratory data analysis (EDA) and feature distribution visualization.
* **scikit-learn**: For machine learning algorithm implementation, data preprocessing, and model evaluation.
* **Yellowbrick**: For visual diagnostics, both in determining the optimal number of clusters
* **joblib**: For saving (exporting) and loading the trained machine learning models for future deployment.

## Machine Learning Models
This project combines two types of machine learning algorithms:
1. **Clustering Model (Segmentation)**: 
   * **K-Means Clustering**: Used to discover natural patterns in the data and form customer segments.
2. **Classification Models (Segment Prediction)**: 
   * **Decision Tree**
   * **Random Forest**

## Methodology
The workflow of this project consists of the following stages:
1. **Data Preprocessing**: Handling missing values, encoding categorical variables, and scaling numerical features to ensure optimal distance metrics for K-Means.
2. **Determining Optimal Clusters**: Utilizing the Elbow Method and Silhouette Visualizer from Yellowbrick to identify the most appropriate number of segments ($K$).
3. **Data Labeling**: Executing the K-Means algorithm to divide customers into segments, then using these segment labels as target variables for the classification phase.
4. **Result Visualization**: Projecting the segmentation results onto a scatter plot, complete with labeled central points (centroids) for each cluster.
5. **Classification Model Training**: Training the Decision Tree and Random Forest models using the customer data to predict the newly generated segment labels.
6. **Model Evaluation**: Assessing and comparing the predictive performance of each algorithm.
7. **Model Saving**: Saving the best classification model using `joblib` for future use.

## Model Evaluation
Since this project utilizes two types of models, the evaluation is conducted in two phases:

**1. Clustering Evaluation:**
* **Silhouette Score**: To measure the separation distance between the resulting clusters.

**2. Classification Evaluation:**
* **Accuracy**, **Precision**, **Recall**, and **F1-Score**.

## Results
The analysis in this project yielded key findings across the two modeling phases:

**1. Clustering (Segmentation) Results**
There are two perspectives on the segmentation results based on the data scaling condition:
* **Pre-Inverse Data** (still in the transformed scale): The customers are divided into 2 main clusters, namely the **Cautious and Thoughtful Customers** profile and the **Young, Fast, and Dynamic Customers** profile.
* **Post-Inverse Data** (returned to the original scale): The cluster interpretation becomes more realistic and can be identified as 2 distinct clusters, namely the **Established Professional Customers** profile and the **Dynamic Student Customers** profile.

**2. Classification Results**
The predictive model training was conducted using the **post-inverse data**. Based on the evaluation results, both tested models (**Random Forest** and **Decision Tree**) demonstrated perfect performance with an evaluation score reaching **100%**. This proves that the customer segment boundaries formed during the clustering phase are highly distinct and consistent, allowing tree-based algorithms to accurately differentiate and classify new customers without any prediction errors.