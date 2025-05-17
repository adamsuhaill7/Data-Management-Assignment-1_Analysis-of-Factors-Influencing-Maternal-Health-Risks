# Data-Management-Assignment-1_Analysis-of-Factors-Influencing-Maternal-Health-Risks
# Analysis of Factors Influencing Maternal Health Risks in Rural Bangladesh

## Course Information
- **Course**: STQD6324 Data Management
- **Topic**: Project 2
- **Student ID**: Adam Suhail Bin Shahril (P153109)

## Project Title
**"Analysis of Factors Influencing Maternal Health Risks in Rural Bangladesh: A Study on Blood Pressure, Blood Sugar, and Heart Rate"**

## Dataset Background
Hello GitHub enthusiasts! My name is Adam, and I'm a master's student in Data Science. For my second entry in my GitHub repository, I have chosen to explore and analyze a new dataset related to maternal health, as it is an increasingly critical issue worldwide. The dataset, collected from rural Bangladesh, focuses on maternal health risks and contains 1,013 records. Each record captures a range of significant health indicators that can influence maternal outcomes globally.

You can access the dataset at the following link: [UCI Machine Learning Repository: Maternal Health Risk Dataset](<insert_link_here>)

### Key Attributes in the Dataset
- **Age**: The age of the women during pregnancy (in years).
- **SystolicBP**: Systolic blood pressure measured in mmHg, a crucial indicator during pregnancy.
- **DiastolicBP**: Diastolic blood pressure measured in mmHg, another significant attribute during pregnancy.
- **BS**: Blood sugar levels measured in mmol/L.
- **BodyTemp**: Body temperature measured in degrees Fahrenheit.
- **HeartRate**: The resting heart rate measured in bpm (beats per minute).
- **RiskLevel**: The predicted risk intensity level during pregnancy, categorized as 'low risk', 'mid risk', or 'high risk'.

This dataset is particularly significant as it highlights the health challenges faced by pregnant women in rural Bangladesh, which resonate across different cultures and healthcare systems. By analyzing these factors, I hope to contribute to a better understanding of maternal health risks and foster discussions around necessary interventions and support systems that can benefit mothers globally.

## Introduction
In today's fast-paced world, maternal health has become an increasingly pressing concern. As a student and future data scientist, I recognize the significant impact of health risks during pregnancy on mothers and their families. This analysis aims to explore the relationship between various health indicators—such as blood pressure, blood sugar levels, and heart rate—and their influence on maternal health outcomes, including risk levels during pregnancy.

### Objectives
- To identify trends in maternal health risks based on blood pressure, blood sugar, heart rate, and other health indicators.
- To examine the correlations between physiological factors and the predicted risk levels during pregnancy.
- To provide insights to inform healthcare interventions and support systems aimed at improving maternal health.

## Problem Statement
In recent years, maternal health has garnered increasing attention, particularly in the context of health risks during pregnancy. This analysis seeks to address several key issues related to the well-being of mothers, focusing on how various factors—such as blood pressure, blood sugar levels, and heart rate—affect maternal health outcomes.

### Main Problems or Hypotheses
- **Blood Pressure and Maternal Health**: Does a higher level of blood pressure correlate with increased risk levels during pregnancy?

#### Guiding Questions
- What is the relationship between systolic and diastolic blood pressure and the risk levels assigned to pregnant women?
- How do these physiological measures influence overall maternal health outcomes?

- **Impact of Blood Sugar Levels**: How do blood sugar levels affect maternal health indicators and risk assessments?

#### Guiding Questions
- How do blood sugar levels correlate with maternal health risks and reported complications?
- What patterns emerge when analyzing the effects of blood sugar on maternal health?

- **Heart Rate and Overall Well-Being**: How does heart rate influence maternal health indicators and risk levels during pregnancy?

#### Guiding Questions
- What is the relationship between heart rate and the predicted risk levels during pregnancy?
- What interventions can be implemented to monitor and manage heart rate for better maternal health outcomes?

By exploring these problems and guiding questions, this analysis aims to provide valuable insights into the health challenges faced by mothers in rural Bangladesh, emphasizing the need for targeted interventions to improve maternal health and contribute to the ongoing discourse surrounding maternal care globally.

## Analysis Overview:

In this analysis, I utilized a Jupyter Notebook within a Hadoop environment, managed via Oracle VirtualBox. The process began by setting up a local Hadoop cluster to facilitate big data processing. Below are the detailed steps I followed to connect Jupyter Notebook to the Hive database and perform visualizations:

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

This structured approach facilitated efficient data management and prepared the dataset for subsequent analysis, ensuring high-quality insights could be derived from the data.
