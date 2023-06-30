# Student Academic Success Classification Analysis
***
![My Image]()

# Overview


# Business Understanding:


The project has the following guiding questions:
*
    - Find trends in the
* Which  makes the most s?
    - Find .
* Which  make the most profit ?
    - Determine pattern among successful .

 # Data Understanding and Analysis
***
## Source of Data
The datasets used in this project are from the following sources:
* [Source name](url)
   - Type:
      - Resources used: The following tables:
          -
            - contains information about the following attributes:
              - name  &larr; string
              - name &larr; string
              - name &larr; string
              - name &larr; int
              - name &larr; float
              - name &larr; string

## Description of Data
***
In order to determine answers to my guiding questions, first I needed to import relevant libraries and packages.

- <code>sqlite3</code>: a library that provides a SQL interface that allows accessing and manipulating SQL database
- <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
- <code>numpy</code>: a key library that brings the computationaly power of languages like C to Python
- <code>matplotlib</code>: a comprehensive visualization library
- <code>seaborn</code>: a data visualization library based on matplotlib

I used methods like <code>.info()</code>, <code>.head()</code> to review data shape and statistics. I alos used <code>.dropna()</code> to remove missing values from dataframes if that data was less than 1% of the overall data within a column. I replaced values by using a combination of <code>.fillna()</code> and <code>.median()</code> replace missing values with the median value. I combined dataframes using <code>.merge()</code> and <code>.replace()</code>to ensure that dataframe queries yielded results that I could analyze.


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

Please review my full analysis in [my Jupyter notebook](link to notebook) or [my presentation](link to pdf of presentation).
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
