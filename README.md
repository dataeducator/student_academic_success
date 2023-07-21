# Student Academic Success Classification Analysis
***
![md-duran-1VqHRwxcCCw-unsplash](https://github.com/dataeducator/student_academic_success/assets/107881738/7ceeaca1-99f5-41fd-bbf6-9b0b1458d47b)

# Business Understanding:
* __Stakeholder__: Instituto Politecnico de Portalegre
* __Business Case__: I have been tasked by the Instituto Politecnico de Portalegre to accurately classify students' academic success. Researchers at the Instituto Politecnico de Portalegre want to reduce the rate of student academic failure in higher education. 

# Overview
In this case, the goal is craft a reliable model that can be refined over time as more information becomes available by using machine learning techniques to identify which students are at risk at ealier stages of their academic path in order to put strategies to support students in place to mitigate their likelihood of dropping out of higher education.While the model will be created with data from higher education instutionstudents in Portugal, the lag in academic success within higher education is also a challenge within the United States. Colleges and Universities face the ever pressing challgence of identifying students who are at risk of not graduating on time and providing effective interventions to move those students back onto a positive pathway to graduation. 

# Data Understanding and Analysis
***
In this project I will use the OSEMiN pipeline to:

* Obtain → Import the data.
* Scrub → Manage the datatypes, resolve missing data or duplicates.
* Explore → Identify patterns within the relationships between variables in the data.
* Model → Create a set of predictive models.
* iNterpret → Identify insights and create visualiations of findings.

## Source of Data
The University of California (Irvine) hosts a machine learning repository with datasets that can be evaluated using machine learning techniques. The dataset used in this exploration can be found [here](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success). This datset was created as a part of a project to reduce academic dropout and failure rates in higher edcuation by leveraging machine learning to identify at risk students early within their academic careers and provide them support to improve their likelihood of on time graduation.  


## Description of Data
***
The data can be found in the data folder of this repository includes information that is known from the time a student enrolls until their second semester of enrollment including their:
- academic path
- demographics
- social-economic factors

The Instituto Politecnico de Protalegre students' dropout and academic Dataset includes sales data contains data for __4424 students with 37 features__ including but not limited to:
| Name               | Description                 |Final Datatype|Numeric or Categorical|Target or Feature|
|--------------------|-----------------------------|---------|-------------------------|-----------------|
| <code>Marital status</code>    |Unique identifier for a house| <code>int</code>|Categorical|Feature|
| <code>Application order</code>|School choice rank on a scale of 0 to 9|<code>int</code>| Categorical|Feature|
| <code>Previous qualification</code>|Highest degree level prior to enrollment|<code>int</code>|Categorical|Feature|
| <code>Age at enrollment</code>|Student age at enrollment|<code>int</code>|Numeric|Feature|
| <code> Target</code>| academic status in one of three classes: dropout, enrolled, graduate|<code>string</code>|Categorical|Target|

There are three classifications of students within this dataset:
- dropout
- enrolled
- graduate

The data was preprocessed to address missing values and anomalies. I am going to use a minimum of 4 machine learning algorithms to classify this data and will also use exploration to determine the following guiding quesions:

- How does marital status influece the likelihoon of students graduating on time?
- Does the timely payment of tuition fees have any impact on the graduation status of students?
- Is there are relationship between the parents' qualifications and the graduation status of students?
In order to determine answers to my guiding questions, first I needed to import relevant libraries and packages.

* <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
* <code>numpy</code>: a key library that brings the computationaly power of languages like C to Python
* <code>matplotlib</code>: a comprehensive visualization library
* <code>seaborn</code>: a data visualization library based on matplotlib
* <code>statsmodels</code>: a library used to understand statistical relationships between variables, often used in the field of economics.
* <code>sklearn</code>: a machine learning libary for data processing and modeling.


## Obtain
The <code> ObtainData </code>class defines a constructor to initialize the data_path attribute and set data to None. It provides a method <code>load_data</code> to load the dataset from the specified data_path using pandas, assuming the dataset is in .csv format with semicolons as the separator, and assigns the loaded data to the data attribute. 
The <code>obtain_data</code> method calls the <code>load_data</code> method and returns the loaded dataset.

## Scrub
The <code>ScrubData</code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides a method check_placeholders to identify the presence of placeholders *(e.g., '?', '#', 'NaN', 'null', 'N/A', '-')* throughout the entire DataFrame. If any placeholders are found, they are replaced; otherwise, a message indicating that no placeholders were detected is printed.

Additionally, the class includes a <code>clean</code> method to perform data cleaning operations. In this method, rows containing missing data are removed using  <code>dropna</code> function, and the resulting cleaned DataFrame is returned.

## Explore
The <code>ExploreData </code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides methods for examining the structure of the dataset, checking and dropping duplicates, generating and displaying a correlation matrix heatmap, plotting a pairplot, and filtering a correlation table based on specified thresholds. Additionally, the class includes methods for plotting the gender distribution, dropout distribution by gender, and the target variable distribution for college students in the dataset. These visualizations aid in exploring and understanding the dataset's characteristics and relationships between variables.

The <code>AnalyzeData</code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides the analyze method to perform data analysis and generate various bar charts and boxplots to examine the influence of different features on graduation status. The class includes methods to map and revise variable values, filter relevant columns, and plot bar charts and boxplots using seaborn and matplotlib. The visualizations aim to gain insights into how various factors such as age range, curricular units, tuition fees, scholarship status, and previous qualification impact graduation status. The different visualizations facilitate the exploration of potential patterns and relationships in the data to support decision-making and interventions for improving graduation rates at Instituto Politecnico de Portalegre.
###  Question 1:How does the number of credits students enrolled in each semester influece the likelihoon of students graduating on time??
***
For the first question I looked for correlations between the graduation status of students and the enrollment patterns of students each semester.  

### Visualization for Question 1

![EDA_for_Question_1](Images/EDA_for_Question_1.png)

### Question 2: Does the timely payment of tuition fees have any impact on the graduation status of students??
***
For the second question I looked at tuition fee payments for each of the three classes.

### Visualization for Question 2

![EDA_for_Question_2](Images/EDA_for_Question_2.png)

### Question 3: Is there are relationship between the age a students is at enrollment and the graduation status of students? ?
***
For the third question I looked at looked for correlations between the age a student was at enrollment and their graduation status along with visualizations created with <code>seaborn</code> and <code>matplotlib</code>

### Visualization for Question 3

![EDA_for_Question_3](Images/EDA_for_Question_3.png)
## Model

## iNterpret
***
## Insights
### Insight 1: Curricular Units in 2nd Semester Matter
Focusing on students' progress and success in their 2nd-semester curricular units can significantly contribute to reducing the rate of academic failure.

### Insight 2: Monitoring Tuition Fee Payments is Pivotal
By closely monitoring and supporting students to stay on track with tuition fee payments, institutions can foster an environment that reduces the rate of academic failure.

### Insight 3: Evaluations and Grades are Crucial
Prioritizing academic support and intervention based on early evaluations and grades can effectively contribute to minimizing the rate of academic failure.


# Future Work
* Explore how to apply XGBoost, a powerful gradient boosting algorithm to a ternary (3 class) classification model.s.
* Extend the analysis to include US universities may also provide valuable insights. 
* Identifying common factors influencing student success across diverse contexts is possible.

Please review my full analysis in [my Jupyter notebook](https://github.com/dataeducator/student_academic_success/blob/main/student_academic_success.ipynb) or [my presentation](link to pdf of presentation).
You may reach out to __Tenicka Norwood__ at tenicka.norwood@gmail.com if you have additional questions.

# Repository Structure
***
<pre>
   .
   └──student_academic_success_project/
      ├── README.md                                            Overview for project reviewers  
      ├── student_academic_success.ipynb                       Documentation of Full Analysis in Jupyter notebook
      ├── presentation                                         PDF version of Full Analysis shown in a slidedeck
      ├── notebook                                             PDF version of Full Analysis shown in Jupyter notebook
      ├── Data/                                                Externally sourced data  
      ├── Images/                                              Includes images generated from python code and sourced externally
      └── .gitignore                                           Specifies intentionally untracked files
 </pre>
