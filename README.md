# Student Academic Success Classification Analysis
***




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
The data includes information that is known from the time a student enrolls including their:
- academic path
- demographics
- social-economic factors

There are three classifications of students within this dataset:
- dropout
- enrolled
- graduate

The data was preprocessed to address missing values and anomalies. The dataset has __37__ columns with __4424__ rows of data. I am going to use a minimum of 4 machine learning algorithms to classify this data and will also use exploration to determine the following guiding quesions:

- How does marital status influece the likelihoon of students graduating on time?
- Does the timely payment of tuition fees have any impact on the graduation status of students?
- Is there are relationship between the parents' qualifications and the graduation status of students?
In order to determine answers to my guiding questions, first I needed to import relevant libraries and packages.

* <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
* <code>numpy</code>: a key library that brings the computationaly power of languages like C to Python
* <code>matplotlib</code>: a comprehensive visualization library
* <code>seaborn</code>: a data visualization library based on matplotlib
* <code>statsmodels</code>: a library used to understand statistical relationships between variables, often used in the field of economics.
* <code>selenium</code>:a library used to perform web testing tasks, useful for scraping data 
* <code>geopy</code>: a library that converts addresses in to geographical locations and vice versa
* <code>requests</code>: a library that make HTTP requests and interacts with web services


# Question 1:?
***
For the first question I looked for .... I explored data related to this question using .... created with <code>seaborn</code> and <code>matplotlib</code>.

## Visualization for Question 1

![EDA_for_Question_1](Images/EDA_for_Question_1.png)

# Question 2:  ?
***
For the second question I looked at ... I explored this question by ...<cod>.sort_values()</code> along with visualizations created with <code>seaborn</code> and <code>matplotlib</code>

## Visualization for Question 2

![EDA_for_Question_2](Images/EDA_for_Question_2.png)

# Question 3: ?
***
For the third question I looked at looked for . I explored this question by ... using <cod>.sort_values()</code> along with visualizations created with <code>seaborn</code> and <code>matplotlib</code>

## Visualization for Question 3

![EDA_for_Question_3](Images/EDA_for_Question_3.png)

# Conclusion
***
## Insights
paragraph with callouts

## Recommendations
paragraph with callouts

# Future Work
*
*

Please review my full analysis in [my Jupyter notebook](https://github.com/dataeducator/student_academic_success/tree/main) or [my presentation](link to pdf of presentation).
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
