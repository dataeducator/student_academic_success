# Student Academic Success Classification Analysis
***





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
* [UC Irvine Machine Learning Repository](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success)
   - Type:
      - Resources used: The following tables:
          -
            - contains information about the following attributes:
|Name | Role | Type| Data Type   |Description | 
|-------|---------|----- |------------- |----------|
|Marital status| Feature| Discrete|int|1 &mdash; single 2 &mdash; married 3 &mdash; widowed 4 &mdash; divorced 5 &mdash; facto union  6 &mdash; legally separated| 
|Application mode|Feature|Discrete|int |1 &ndash; 1st phase &ndash; general contingent 2 &ndash;Ordinance No. 612/93 <br> 5 &ndash; 1st phase &ndash; special contingent (Azores Island) 7&ndash; Holders of other higher courses 10 &ndash; Ordinance No. 854-B/99 15 &ndash;International student (bachelor) 16 &ndash; 1st phase &ndash; special contingent (Madeira Island) 17 &ndash; 2nd phase &ndash; general contingent 18 &ndash; 3rd phase &ndash; general contingent 26 &ndash; Ordinance No. 533-A/99, item b2) (Different Plan) 27 - Ordinance No. 533-A/99, item b3 (Other Institution) 39 &ndash; Over 23 years old 42 &ndash; Transfer 43 &ndash; Change of course 44 &ndash; Technological specialization diploma holders 51 &ndash; Change of institution/course 53 &ndash; Short cycle diploma holders 57 &ndash; Change of institution/course (International)|
|Application order|Feature|Discrete|int|Application order <br> between 0 - first choice; and 9 last choice|
|Course|Feature|Discrete|int |33 - Biofuel Production Technologies 171 - Animation and Multimedia Design 8014 - Social Service (evening attendance) 9003 - Agronomy 9070 - Communication Design 9085 - Veterinary Nursing 9119 - Informatics Engineering 9130 - Equinculture 9147 - Management 9238 - Social Service 9254 - Tourism 9500 - Nursing 9556 - Oral Hygiene 9670 - Advertising and Marketing Management 9773 - Journalism and Communication 9853 - Basic Education 9991 - Management (evening attendance)|	
|Daytime/evening attendance|Feature|Discrete|int|1 &mdash; daytime 0 &mdash; evening|
|Previous qualification|Feature|Discrete|int|1  &ndash; Secondary education 2  &ndash; Higher education - bachelor's degree 3  &ndash; Higher education - degree 4  &ndash; Higher education - master's    <br> 5&ndash; Higher education - doctorate   6  &ndash; Frequency of higher education 9 - 12th year of schooling - not completed 10 - 11th year of schooling - not completed 12  &ndash; Other  &ndash; 11th year of schooling  14  &ndash; 10th year of schooling 15  &ndash; 10th year of schooling - not completed 19 - Basic education 3rd cycle (9th/10th/11th year) or equiv. 38  &ndash; Basic education 2nd cycle (6th/7th/8th year) or equiv. <br>39  &ndash; Technological specialization course 40  &ndash; Higher education - degree (1st cycle) 42  &ndash; Professional higher technical course<br> 43  &ndash; Higher education - master (2nd cycle)|
|Previous qualification (grade)|Feature|Continuous|float|Grade of previous qualification <br> between 0 and 200|
|Nacionality|Feature|Discrete||1 &mdash; Portuguese; 2 &mdash; German; 6 &mdash; Spanish; 11 &mdash; Italian; 13 &mdash; Dutch; 14 &mdash; English; 17 &mdash; Lithuanian; 21 &mdash; Angolan; <br>22 &mdash; Cape Verdean; 24 &mdash; Guinean; 25 &mdash; Mozambican; 26 &mdash; Santomean; 32 &mdash; Turkish; 41 &mdash; Brazilian; 62 &mdash; Romanian; <br> 100 &mdash; Moldova (Republic of); 101 &mdash; Mexican; 103 &mdash; Ukrainian; 105 &mdash; Russian; 108 &mdash; Cuban; 109 &mdash; Colombian|
|Mother's qualification|Feature|Discrete|int|1 - Secondary Education - 12th Year of Schooling or Eq. 2 - Higher Education - Bachelor's Degree 3 - Higher Education - Degree 4 - Higher Education - Master's 5 - Higher Education - Doctorate 6 - Frequency of Higher Education 9 - 12th Year of Schooling - Not Completed 10 - 11th Year of Schooling - Not Completed 11 - 7th Year (Old) 12 - Other - 11th Year of Schooling 14 - 10th Year of Schooling 18 - General commerce course 19 - Basic Education 3rd Cycle (9th/10th/11th Year) or Equiv. 22 - Technical-professional course 26 - 7th year of schooling 27 - 2nd cycle of the general high school course 29 - 9th Year of Schooling - Not Completed 30 - 8th year of schooling 34 - Unknown 35 - Can't read or write 36 - Can read without having a 4th year of schooling 37 - Basic education 1st cycle (4th/5th year) or equiv. 38 - Basic Education 2nd Cycle (6th/7th/8th Year) or Equiv. 39 - Technological specialization course 40 - Higher education - degree (1st cycle) 41 - Specialized higher studies course 42 - Professional higher technical course 43 - Higher Education - Master (2nd cycle) 44 - Higher Education - Doctorate (3rd cycle)|
|Father's qualification|Feature|Discrete|int|	1 - Secondary Education - 12th Year of Schooling or Eq. 2 - Higher Education - Bachelor's Degree 3 - Higher Education - Degree 4 - Higher Education - Master's 5 - Higher Education - Doctorate 6 - Frequency of Higher Education 9 - 12th Year of Schooling - Not Completed 10 - 11th Year of Schooling - Not Completed 11 - 7th Year (Old) 12 - Other - 11th Year of Schooling 13 - 2nd year complementary high school course 14 - 10th Year of Schooling 18 - General commerce course 19 - Basic Education 3rd Cycle (9th/10th/11th Year) or Equiv. 20 - Complementary High School Course 22 - Technical-professional course 25 - Complementary High School Course - not concluded 26 - 7th year of schooling 27 - 2nd cycle of the general high school course 29 - 9th Year of Schooling - Not Completed 30 - 8th year of schooling 31 - General Course of Administration and Commerce 33 - Supplementary Accounting and Administration 34 - Unknown 35 - Can't read or write 36 - Can read without having a 4th year of schooling 37 - Basic education 1st cycle (4th/5th year) or equiv. 38 - Basic Education 2nd Cycle (6th/7th/8th Year) or Equiv. 39 - Technological specialization course 40 - Higher education - degree (1st cycle) 41 - Specialized higher studies course 42 - Professional higher technical course 43 - Higher Education - Master (2nd cycle) 44 - Higher Education - Doctorate (3rd cycle|
|Mother's occupation|Feature|Discrete|int|0 &ndash; Student 1 &ndash;  Representatives of the Legislative Power and Executive Bodies, Directors, Directors and Executive Managers 2 &ndash;  Specialists in Intellectual and Scientific Activities 3 &ndash;  Intermediate Level Technicians and Professions 4 &ndash;  Administrative staff 5 &ndash;  Personal Services, Security and Safety Workers and Sellers 6 &ndash;  Farmers and Skilled Workers in Agriculture, Fisheries and Forestry 7 &ndash;  Skilled Workers in Industry, Construction and Craftsmen 8 &ndash;  Installation and Machine Operators and Assembly Workers 9 &ndash;  Unskilled Workers 10 &ndash;  Armed Forces Professions 90 &ndash; Other Situation <br>99&ndash;  (blank) 122 &ndash;  Health professionals 123 - teachers 125 - Specialists in information and communication technologies (ICT) 131 - Intermediate level science and engineering technicians and professions 132 - Technicians and professionals, of intermediate level of health 134 - Intermediate level technicians from legal, social, sports, cultural and similar services 141 - Office workers, secretaries in general and data processing operators 143 - Data, accounting, statistical, financial services and registry-related operators 144 - Other administrative support staff 151 - personal service workers 152 - sellers 153 - Personal care workers and the like 171 - Skilled construction workers and the like, except electricians 173 - Skilled workers in printing, precision instrument manufacturing, jewelers, artisans and the like 175 - Workers in food processing, woodworking, clothing and other industries and crafts 191 - cleaning workers 192 - Unskilled workers in agriculture, animal production, fisheries and forestry 193 - Unskilled workers in extractive industry, construction, manufacturing and transport 194 - Meal preparation assistants|
|Father's occupation|Feature|Discrete|int|0 &ndash; Student 1 &ndash; Representatives of the Legislative Power and Executive Bodies, Directors, Directors and Executive Managers <br>2 &ndash; Specialists in Intellectual and Scientific Activities 3 &ndash;Intermediate Level Technicians and Professions 4 &ndash; Administrative staff <br>5 &ndash; Personal Services, Security and Safety Workers and Sellers 6 &ndash; Farmers and Skilled Workers in Agriculture, Fisheries and Forestry 7 &ndash; Skilled Workers in Industry, Construction and Craftsmen 8 &ndash; Installation and Machine Operators and Assembly Workers 9 &ndash; Unskilled Workers 10 &ndash; Armed Forces Professions 90 &ndash; Other Situation 99 &ndash; (blank) 101 &ndash; Armed Forces Officers <br>102 &ndash; Armed Forces Sergeants 103 &ndash; Other Armed Forces personnel 112 &ndash; Directors of administrative and commercial services 114 &ndash; Hotel, catering, trade and other services directors 121 - Specialists in the physical sciences, mathematics, engineering and related techniques 122 - Health professionals 123 - teachers 124 - Specialists in finance, accounting, administrative organization, public and commercial relations 131 - Intermediate level science and engineering technicians and professions 132 - Technicians and professionals, of intermediate level of health 134 - Intermediate level technicians from legal, social, sports, cultural and similar services 135 - Information and communication technology technicians 141 - Office workers, secretaries in general and data processing operators 143 - Data, accounting, statistical, financial services and registry-related operators 144 - Other administrative support staff 151 - personal service workers 152 - sellers 153 - Personal care workers and the like 154 - Protection and security services personnel 161 - Market-oriented farmers and skilled agricultural and animal production workers 163 - Farmers, livestock keepers, fishermen, hunters and gatherers, subsistence 171 - Skilled construction workers and the like, except electricians 172 - Skilled workers in metallurgy, metalworking and similar 174 - Skilled workers in electricity and electronics 175 - Workers in food processing, woodworking, clothing and other industries and crafts 181 - Fixed plant and machine operators 182 - assembly workers 183 - Vehicle drivers and mobile equipment operators 192 - Unskilled workers in agriculture, animal production, fisheries and forestry 193 - Unskilled workers in extractive industry, construction, manufacturing and transport <br>194 - Meal preparation assistants 195 - Street vendors (except food) and street service providers|
|Admission grade|Feature|Continuous|float|Admission grade (between 0 and 200)|
|Displaced|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|Educational special needs|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|Debtor|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|Tuition fees up to date|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|Gender|Feature|Discrete|int|1 &mdash; male 0 &mdash; female|
|Scholarship holder|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|Age at enrollment|Feature|Discrete|int|Age of studend at enrollment|
|Scholarship holder|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|International|Feature|Discrete|int|1 &mdash; yes 0 &mdash; no|
|Curricular units 1st sem (credited)|Feature|Discrete|int|Number of curricular units credited in the 1st semester|
|Curricular units 1st sem (enrolled)|Feature|Discrete|int|Number of curricular units enrolled in the 1st semester|
|Curricular units 1st sem (evaluations)|Feature|Discrete|int|Number of evaluations to curricular units in the 1st semester|
|Curricular units 1st sem (approved)|Feature|Discrete|int|Number of curricular units approved in the 1st semester|
|Curricular units 1st sem (grade)|Feature|Discrete|float|Grade average in the 1st semester (between 0 and 20)|
|Curricular units 1st sem (without evaluations)|Feature|Discrete|int|Number of curricular units without evalutions in the 1st semester|
|Curricular units 2nd sem (credited)|Feature|Discrete|int|Number of curricular units credited in the 2nd semester|
|Curricular units 2nd sem (enrolled)|Feature|Discrete|int|Number of curricular units enrolled in the 2nd semester|
|Curricular units 2nd sem (evaluations)|Feature|Discrete|int|Number of evaluations to curricular units in the 2nd semester|
|Curricular units 2nd sem (approved)|Feature|Discrete|int|Number of curricular units approved in the 2nd semester|
|Curricular units 2nd sem (grade)|Feature|Discrete|float|Grade average in the 2nd semester (between 0 and 20)|
|Curricular units 2nd sem (without evaluations)|Feature|Discrete|int|Number of curricular units without evalutions in the 1st semester|
|Unemployment rate|Feature|Continuous|float|Unemployment rate (%)|
|Inflation rate|Feature|Continuous|float|Inflation rate (%)|
|GDP|Feature|Continuous|float|GDP|
|Target|Target|Categorical|string|Target. The problem is formulated as a three category classification task (dropout, enrolled, and graduate) at the end of the normal duration of the course|


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
