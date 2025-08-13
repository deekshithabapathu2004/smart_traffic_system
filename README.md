# **Intelligent Urban Traffic Flow Forecasting and Anomaly Detection**

## **Project Overview**

This project presents an end-to-end data science solution for a critical urban challenge: predicting and managing traffic congestion. Using a real-world, large-scale traffic dataset, I have developed an advanced deep learning model to forecast traffic flow and a complementary system to detect significant, anomalous traffic events.

The solution is built to be a robust, data-driven tool for city planners and traffic management authorities, enabling proactive decision-making to improve urban mobility and safety.

## **Problem Statement**

Traditional traffic management relies on historical patterns and reactive measures. This project addresses the need for a predictive system that can:

1. **Accurately forecast** future traffic speeds to anticipate congestion.  
2. **Detect and flag anomalous events** (e.g., accidents, road closures) that deviate from predicted patterns.  
3. **Provide clear, visual insights** for non-technical stakeholders to make informed decisions.

## **Data**

The project utilizes the **PEMS-BAY** dataset, a globally recognized benchmark for spatio-temporal traffic forecasting. The dataset contains:

* Traffic speed data from **325 sensors** in the Bay Area, California.  
* Over **6 months** of data, recorded at **5-minute intervals**.  
* A total of **52,116 time steps**, providing a rich source of information for training a robust model.

## **Methodology**

The project followed a complete data science pipeline, from data engineering to model deployment and visualization.

### **1\. Data Preprocessing & Feature Engineering**

* **Data Loading:** The raw data was loaded from a large .h5 file using h5py.  
* **Feature Engineering:** I created new time-based features such as dayofweek, hour, and minute to help the model identify recurring temporal patterns (e.g., weekday morning vs. weekend afternoon).  
* **Data Normalization:** Traffic speed data was normalized using MinMaxScaler to optimize deep learning model training.  
* **Sequence Creation:** The time series data was transformed into a sequential format, with each input sequence containing **12 historical time steps (1 hour)** and each output sequence predicting the **next 6 time steps (30 minutes)**.

### **2\. Deep Learning Model Development**

* **Model Choice:** I chose a **Transformer-based neural network** for its ability to effectively capture long-range dependencies and complex patterns in sequential data.  
* **Architecture:** The model consists of a custom TransformerBlock with multi-head attention and feed-forward networks, designed to learn the spatio-temporal correlations in the traffic data.  
* **Training:** The model was trained for 100 epochs on a **Google Colab GPU** to ensure an efficient and high-quality training process.

### **3\. Model Evaluation & Anomaly Detection**

* **Performance Metrics:** The trained model achieved a **Mean Absolute Error (MAE) of 2.47**, indicating that its speed predictions were, on average, only off by 2.47 units. The model also achieved an **R-squared score of 0.6458**, demonstrating that it explains approximately 65% of the variance in the traffic data.  
* **Anomaly Detection:** Anomaly detection was performed by identifying prediction errors that were more than **3 standard deviations** from the mean error. This statistical approach allowed the system to highlight significant and unexpected traffic events.

### **4\. Dashboard & Visualization**

* The project culminates in a professional, interactive dashboard created with **Microsoft Power BI**.  
* The dashboard allows users to visualize a comparison of **True vs. Predicted speeds**, track the model's **overall accuracy (MAE)**, and identify the **most severe anomalies** by sensor and time.

## **Skills Demonstrated**

* **Machine Learning & Deep Learning:** Time-series forecasting, Transformer architecture, TensorFlow, Keras.  
* **Data Engineering:** Data cleaning, feature engineering, data normalization, Pandas, NumPy.  
* **Data Visualization & Analysis:** Dashboard creation with **Power BI**, statistical analysis of model performance.  
* **Software Engineering:** Project structure, version control with **Git** and **Git LFS**.  
* **Cloud Computing:** Utilizing **Google Colab's GPU** for accelerated model training.

## **Conclusion**

This project successfully demonstrates an end-to-end data science workflow to solve a real-world problem. It showcases my ability to not only build and train advanced deep learning models but also to translate complex technical results into clear, actionable insights for business use.