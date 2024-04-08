# DDoS Detection using Apache Spark and HDFS

## 1. Motivation and Problem Statement
In today's digital era, as the use of online services continues to grow, individuals and enterprises frequently suffer from different types of web attacks such as Distributed Denial of Service (DDoS) and information leak. In this condition, anomaly detection has become significant in protecting internet traffic. Some anomaly behaviors, especially DDoS, send a huge volume of abnormal traffic to the victim host in a short time. The main challenge in this process is handling the immense volume of network data efficiently. 

Problem statement: In this project, we plan to perform DDoS detection to efficiently process a huge volume of real-world network traffic by Apache Spark and HDFS.


## 2. Approaches
Our proposed solution involves leveraging big data processing frameworks like Apache Spark and HDFS for handling and analyzing massive volumes of network log data. On top of that, we plan to utilize machine learning algorithms implemented using Python libraries such as Scikit-learn, TensorFlow, or PyTorch, facilitated by the Ray cluster for model training to predict traffic trends and detect anomalous behavior. Additionally, we intend to employ ChatGPT for data visualization to aid in understanding analysis outcomes.

### 2.1 System Design
Our whole system consists of two subsystems, which are the data processing system and the model training system. In terms of the data processing system, we will Utilize Apache Spark for parallel data processing of network logs stored in HDFS. For the model training system, a Ray cluster will be set up for distributed training of machine learning models using scikit-learn. These two clusters will be deployed on AWS EC2 t3.large machines. Regarding the integration layer design, once the data is preprocessed and features are extracted using Spark, it can be serialized and passed to Ray by leveraging the Ray API for inter-process communication. After that, machine learning models can be trained using scikit-learn or any other ML library supported by Ray.

### 2.2 Dataset
We choose the CAIDA UCSD DDos 2007 attack dataset which has a total size of 21 GB and covers about one hour of anonymized traffic traces from a DDoS attack on August 4, 2007.


### 2.3 Data Preprocessing
Our first step involves cleaning the collected data utilizing Apache Spark for scalable and distributed data processing. This process includes removing irrelevant information, standardizing date-time formats, and handling missing or erroneous data points to ensure the data's quality and consistency.


### 2.4 Feature Engineering
To extract meaningful insights, we'll perform feature engineering. This entails identifying and extracting relevant features such as request frequency, traffic volume, source IP addresses, geographical locations, user agents, and more. These features will serve as the basis for our analysis and modeling efforts.


### 2.5 Model Selection and Training
We'll delve into selecting appropriate machine learning algorithms tailored to our specific use case. This involves exploring algorithms suitable for tasks like time series forecasting for traffic trends prediction and anomaly detection for identifying malicious activities such as DDoS attacks. Following selection, we'll train these models using our preprocessed data leveraging Python libraries such as Scikit-learn, TensorFlow, or PyTorch for machine learning model development. Ray cluster will facilitate distributed training and optimization.


### 2.6 Model Evaluation and Performance Tuning
Once trained, we'll rigorously evaluate the performance of our models. This evaluation includes metrics assessment and comparison to benchmarks. Furthermore, we'll iterate on our models, fine-tuning parameters and exploring alternative algorithms to optimize performance and accuracy.


### 2.7 Identification System
With trained models in hand, we'll implement a robust system for real-time or batch traffic analysis. This system will leverage the trained models to identify anomalies and potential security threats within the network logs. Detection mechanisms will be integrated to swiftly flag instances of suspicious activities, such as DDoS attacks, for further investigation or mitigation.


### 2.8 Visualization
To provide users with intuitive insights, we'll develop a visualization interface. This interface will effectively represent the analyzed data, showcasing key trends, anomalies, and security alerts. Integration with ChatGPT will enhance the user experience by providing natural language explanations of the visualizations, aiding in interpretation and decision-making.


