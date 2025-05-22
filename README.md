# 📊 Data Management Assignment 1: Analysis of Factors Influencing Maternal Health Risks

## 📚 Course Information
- **Course**: STQD6324 Data Management
- **Topic**: Assignment 1
- **Student ID**: Adam Suhail Bin Shahril (P153109)

## 📝 Project Title
**"Analysis of Factors Influencing Maternal Health Risks in Rural Bangladesh: A Study on Blood Pressure, Blood Sugar, and Heart Rate"**

![Maternal Health](maternal_health.jpg) <!-- Maternal health image -->

## 📊 Dataset Background
Hello GitHub enthusiasts! I'm Adam, a master's student in Data Science. For my second GitHub entry, I am exploring a dataset related to maternal health, an increasingly critical global issue. This dataset, collected from rural Bangladesh, focuses on maternal health risks and contains **1,013 records** of significant health indicators impacting maternal outcomes.

You can access the dataset here: [UCI Machine Learning Repository: Maternal Health Risk Dataset](https://archive.ics.uci.edu/dataset/863/maternal+health+risk)

### 🔑 Key Attributes in the Dataset
- **Age**: Age of women during pregnancy (in years).
- **SystolicBP**: Systolic blood pressure (mmHg).
- **DiastolicBP**: Diastolic blood pressure (mmHg).
- **BS**: Blood sugar levels (mmol/L).
- **BodyTemp**: Body temperature (°F).
- **HeartRate**: Resting heart rate (bpm).
- **RiskLevel**: Predicted risk intensity during pregnancy ('low risk', 'mid risk', 'high risk').

This dataset is crucial as it highlights the health challenges faced by pregnant women in rural Bangladesh, with implications across various cultures and healthcare systems. My analysis aims to enhance understanding of maternal health risks and stimulate discussions on necessary interventions.

## 🌍 Introduction
Maternal health is a pressing global concern, significantly impacting mothers and their families. This analysis explores the relationships between health indicators—blood pressure, blood sugar levels, and heart rate—and their influence on maternal health outcomes, particularly risk levels.

### 🎯 Objectives
- Identify trends in maternal health risks based on key health indicators.
- Examine correlations between physiological factors and predicted risk levels during pregnancy.
- Provide insights to inform healthcare interventions to improve maternal health.

## ❓ Problem Statement
This analysis addresses key issues related to maternal well-being, focusing on how factors like blood pressure, blood sugar levels, and heart rate affect maternal health outcomes.

### 🔍 Main Problems or Hypotheses
- **Blood Pressure and Maternal Health**: Does higher blood pressure correlate with increased risk levels during pregnancy?
  - **Guiding Questions**:
    - What is the relationship between systolic/diastolic blood pressure and risk levels?
    - How do these measures influence overall maternal health?

- **Impact of Blood Sugar Levels**: How do blood sugar levels affect maternal health indicators and risk assessments?
  - **Guiding Questions**:
    - How do blood sugar levels correlate with maternal health risks?
    - What patterns emerge in analyzing blood sugar effects?

- **Heart Rate and Overall Well-Being**: How does heart rate influence maternal health indicators and risk levels?
  - **Guiding Questions**:
    - What is the relationship between heart rate and predicted risk levels?
    - What interventions can be implemented for better outcomes?

This analysis aims to provide valuable insights into the health challenges faced by mothers in rural Bangladesh, emphasizing the need for targeted interventions to improve maternal health.

## 📈 Analysis Overview
This analysis was conducted using a Jupyter Notebook within a Hadoop environment, managed via Oracle VirtualBox. Here are the detailed steps taken:


1. **Creating a New Conda Environment**:
   - I created a new Conda environment with the necessary dependencies:
     ```bash
     conda create -n <env_name> python=3.8 -y
     conda activate <env_name>
     conda install pandas numpy matplotlib seaborn scikit-learn jupyter
     pip install pyhive thrift thrift-sasl pure-sasl impyla
     conda install -c conda-forge sasl jupyterlab openpyxl plotly
     ```

2. **Connecting Local Machine to VM**:
   - I connected my local machine to the VirtualBox using SSH:
     ```bash
     ssh -L 10000:localhost:10000 maria_dev@127.0.0.1 -p 2222
     ```

3. **Launching Jupyter Notebook**:
   - To run Jupyter Notebook, I opened an Anaconda terminal and executed:
     ```bash
     conda activate <env_name>
     start jupyter notebook
     ```

4. **Connecting to Hive Database**:
   - In a Jupyter Notebook cell, I used the following code to connect to the Hive database:
     ```python
     from impala.dbapi import connect

     conn = connect(
         host='127.0.0.1',
         port=10000,
         user='maria_dev',
         database='default',
         auth_mechanism='PLAIN'
     )
     cursor = conn.cursor()
     cursor.execute('SHOW TABLES')
     print(cursor.fetchall())
     ```

5. **Data Cleaning**:
   - Once connected, I performed various data cleaning tasks within the Jupyter Notebook. This included handling missing values, filtering outliers, and ensuring the data types were correctly assigned for analysis.

6. **Data Visualization**:
   - After the data cleaning process, I created several visualizations to analyze the relationships and distributions of key variables in the dataset. These visualizations provided valuable insights into maternal health indicators.

## 📊 Data Visualizations
Here are the visualizations derived from the analysis:

### Visualization 1
![Visualization 1](Visualization%201.png)

### Visualization 2
![Visualization 2](Visualization%202.png)

### Visualization 3
![Visualization 3](Visualization%203.png)

### Visualization 4
![Visualization 4](Visualization%204.png)

### Visualization 5
![Visualization 5](Visualization%205.png)

### Visualization 6
![Visualization 6](Visualization%206.png)

This structured approach facilitated efficient data management and prepared the dataset for subsequent analysis, ensuring high-quality insights could be derived from the data.

## 📋 Conclusion
The analysis of maternal health risks in rural Bangladesh highlights significant health indicators that can impact pregnancy outcomes. Through this project, I aimed to uncover trends and correlations that can inform healthcare interventions. The insights gained from the visualizations underscore the importance of continuous monitoring and support for maternal health.

## 📄 References
- Ahmed, M. (2020). Maternal Health Risk [Dataset]. UCI Machine Learning Repository. https://doi.org/10.24432/C5DP5D.

This structured approach ensured efficient data management, preparing the dataset for insightful analysis.
