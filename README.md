# Student Academic Success Classification Analysis
***
![md-duran-1VqHRwxcCCw-unsplash](https://github.com/dataeducator/student_academic_success/assets/107881738/7ceeaca1-99f5-41fd-bbf6-9b0b1458d47b)

# Business Understanding:
* __Stakeholder__: Instituto Politecnico de Portalegre
* __Business Case__: I Researchers at the Instituto Politecnico de Portalegre want to reduce the rate of student academic failure in higher education.

# Overview
The aim is to create a dependable model using machine learning techniques to spot students who may be at risk of dropping out of higher education after enrolling. By identifying these students early, we can implement strategies to support them and reduce the likelihood of them leaving college. 

The model was trained and tested with higher education student data from Portugal, but it is relevant for colleges and universities in the United States as well. We also face the challenge of identifying at-risk students and providing interventions to help them graduate on time and succeed in their studies. 
> The completion rates of (US) undergraduates within six years of enrollment stand at only __62.3%__ as of 2022.
>
> -- Hanneh Bareham and Chelsea Wing (bankrate.com)
>
> 

We will prioritize recall in this project over precision. By prioritizing recall, we aim to reduce the number of false negatives and increase the model's ability to correctly identify and intervene with students at risk of academic failure. Minimizing the number of false negatives will help to ensure that fewer students who need educational assistance slip through the cracks and are not appropriately identified and supported.

* True Positive represents the number correctly predicted positive instances.
    * Ex. students bieng predicted to dropout and actually do dropout
* False negatives represent the number of incorrectly predicted negative instances.
    * Ex. students being predicted to dropout but do not dropout

# Data Understanding and Analysis
***
In this project, I will use the OSEMiN pipeline to:

* Obtain → Import the data.
* Scrub → Manage the datatypes, and resolve missing data or duplicates.
* Explore → Identify patterns within the relationships between variables in the data.
* Model → Create a set of predictive models.
* iNterpret → Identify insights and create visualizations of findings.

We will prioritize recall in this project over precision. By prioritizing recall, we aim to reduce the number of false negatives and increase the model's ability to correctly identify and intervene with students at risk of academic failure. Minimizing the number of false negatives will help to ensure that fewer students who need educational assistance slip through the cracks and are not appropriately identified and supported.

* True positives are the cases when a model predicts positive instances correctly.
    - Ex. students predicted to drop out and do drop out
* False negatives are the cases when a model mispredicts negative instances.
    - Ex. students predicted to drop out but do not drop out

## Source of Data
The machine learning repository at the University of California(Irvine) contains dataset for evaluating machine learning techniques. The dataset used in this exploration is from this repository and can be found [here](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success). This dataset was created as a part of a project to reduce academic dropout and failure rates in higher education. Using machine learning, this project aims to identify at-risk students early  and provide support to improve their likelihood of on-time graduation.  


## Description of Data
***
The data can also be found in the data folder of this repository includes information that is known from the time a student enrolls until their second semester of enrollment, including their:
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

We preprocessed the data to address missing values and anomalies. The dataset has 37 columns with 4424 rows of data. I am going to use a minimum of 4 machine-learning algorithms to classify this data and will also use exploration to determine the following:

- How does the number of credits students enrolled in each semester influence the likelihood of students graduating on time?
- Does the timely payment of tuition fees have any impact on the graduation status of students?
- Is there a relationship between the age a student is at enrollment and the graduation status of students?

To determine answers to my guiding questions, first, I needed to import relevant libraries and packages.

* <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
* <code>numpy</code>: a key library that brings the computational power of languages like C to Python
* <code>matplotlib</code>: a comprehensive visualization library
* <code>seaborn</code>: a data visualization library based on matplotlib
* <code>statsmodels</code>: a library used to understand statistical relationships between variables, often used in economics.
* <code>sklearn</code>: a machine learning library for data processing and modeling.

## Modeling

### Obtain
The <code> ObtainData </code>class defines a constructor to initialize the data_path attribute and set data to None. It provides a method <code>load_data</code> to load the dataset from the specified data_path using pandas, assuming the dataset is in .csv format with semicolons as the separator, and assigns the loaded data to the data attribute. 
The <code>obtain_data</code> method calls the <code>load_data</code> method and returns the loaded dataset.

### Scrub
The <code>ScrubData</code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides a method check_placeholders to check for placeholders  *(e.g., '?', '#', 'NaN', 'null', 'N/A', '-')* and replaces them if found;  otherwise, it prints a message indicating that no placeholders were detected.

Additionally, the class includes a <code>clean</code> method to perform data-cleaning operations. In this method, rows containing missing data are removed using  <code>dropna</code> function and the resulting cleaned DataFrame is returned.

### Explore
After obtaining the dataset using the <code>ObtainData</code> class and cleaning it with the <code>ScrubData</code> class, the <coode>ExploreData</code> class can be used to analyze and explore the cleaned dataset further. The <code>ExploreData</code> class allows us to understand the data and identify any patterns or insights that could be beneficial for the subsequent analysis or decision-making processes.

The AnalyzeData class has the following functions:

* <code>analyze</code>: Maps relevant variables to their corresponding labels and analyzes data to explore factors influencing student graduation status.
* <code>plot_bar_chart</code>: Plots bar charts to visualize the impact of categorical variables on graduation status.
* <code>plot_boxplot</code>: Plots box plots to visualize the relationship between target variables and numerical features.
* <code>plot_horizontal_bar_chart</code>: Plots horizontal bar charts to explore the influence of 'Previous qualification' on graduation status.

By using these functions, we can begin to explore the factors affecting graduation outcomes.

During exploration, we identified the following trends:

* Age Range and Graduation: 25-35 age group has higher enrollment and graduation rates. Age 50+ has higher dropout.
* Curricular Units and Graduation: 4-6 units show the highest graduation rate, 7+ slightly lower, and 0-3 lower.
* Tuition Fees and Graduation: Up-to-date fees link to significantly higher graduation rates.
* Marital Status and Graduation: Married/in a union have a higher graduation rate.
* Previous Qualification: Higher education levels have higher graduation rates. Basic education lower rates.

I will combine this information with the results of a ternary classifier that is trained on 80% of the dataset to identify insights that will make an impact on decreasing failure rates for students in higher education.

###  Question 1:How does the number of credits students enrolled in each semester influence the likelihood of students graduating on time?
***
For the first question, I looked for correlations between the graduation status of students and the enrollment patterns of students each semester.  

### Visualization for Question 1

<img width="514" alt="EDA for Question 1a" src="https://github.com/dataeducator/student_academic_success/assets/107881738/df8596b8-ae17-4cda-925c-285e741d13d1">

<img width="508" alt="EDA for Question 1b" src="https://github.com/dataeducator/student_academic_success/assets/107881738/0453827a-316d-4b22-a5b9-48cf596d1435">

### Question 2: Does the timely payment of tuition fees have any impact on the graduation status of students?
***
For the second question, I looked at tuition fee payments for each class.

### Visualization for Question 2
<img width="476" alt="EDA for Question 2" src="https://github.com/dataeducator/student_academic_success/assets/107881738/efe9f06b-62d6-45b2-b509-8bcb9a9a7127">


### Question 3: Is there a relationship between the age a student is at enrollment and the graduation status of students?
***
For the third question, I looked at looked for correlations between the age a student was at enrollment and their graduation status, along with visualizations created with <code>seaborn</code> and <code>matplotlib</code>

### Visualization for Question 3

<img width="484" alt="EDA for Question 3" src="https://github.com/dataeducator/student_academic_success/assets/107881738/26970cc4-0009-4d72-a808-7d78411f7a34">

### Model
The <code>TernaryClassifier</code> is a class designed to perform classification tasks on datasets with a ternary (three-class) target variable. It provides methods for data preprocessing, training multiple classification models, making predictions, and tuning hyperparameters to optimize model performance.

The name "TernaryClassifier" is derived from the term "ternary," which refers to systems or situations that involve three elements or options. A ternary classification problem involves predicting one of three possible classes or categories for each data instance.

The <code>TernaryClassifier</code> class includes:

* Constructor: Takes a DataFrame (<code>data</code>) containing features (X) and ternary target variable (y).

* Preprocessing: Separates X and y, scales features using <code>StandardScaler</code>, encodes y with <code>LabelEncoder</code>, and returns the scaled features as a DataFrame.

* Model Library: Defines models for training, including <code>Logistic Regression</code>, <code>K-Nearest Neighbors</code>, <code>Support Vector Machine</code>, <code>Decision Trees</code>, and <code>Random Forests</code>.

* Training: Trains each model in the library on preprocessed data (X and y), making them ready for prediction.

* Prediction: Predicts target variable values using all trained models on testing data (X_test), returning a dictionary of model predictions.

* Hyperparameter Tuning: Uses <code>tune_parameters()</code> method to optimize model performance by finding the best hyperparameters for each classifier using <code>GridSearchCV</code>.

* Training with Parameter Tuning: Trains models with tuned hyperparameters using <code>GridSearchCV</code>. Returns a dictionary of best models and identifies the most performative one based on recall scores.

Each of the models was trained using an 80/20 split and then evaluated using recall.

### Evaluation
I created a <code>ModelEvaluation</code> class to evaluate different classifier models for a ternary classification problem. The class contains: 

* methods to calculate evaluation metrics such as accuracy, precision, recall, and F1 score for each trained model. 

*  functions to analyze feature importances for the <code>RandomForestClassifier</code> and identify the best hyperparameters that yield the best recall score for each model using cross-validation.

The class includes the following functions: 
* <code>evaluate_models</code> &rarr; takes a trained <code>TernaryClassifier</code> instance, performs predictions on the test data, and calculates various evaluation metrics for each model. 

* <code>analyze_feature_importances</code> &rarr; analyze feature importances for the <code>RandomForestClassifier</code> and stores them in a data frame. 
    
* <code>calculate_best_scores</code> &rarr; <code>GridSearchCV</code> to find the best hyperparameters for each model based on a specified scoring metric. 
    
* <code>identify_best_parameters</code> &rarr; identify the best hyperparameters and their corresponding recall scores for each model.

* <code>plot_feature_importances</code> &rarr; plot the feature importances of the trained models using bar plots.

<img width="656" alt="ModelEvaluation" src="https://github.com/dataeducator/student_academic_success/assets/107881738/de02951d-7543-4f86-bfe8-cf2c2a5e5915">

The <code>evaluate_models</code> method takes a trained <code>TernaryClassifier</code> instance, performs predictions on the test data, and calculates various evaluation metrics for each model.

![Confusion Matrix Random Forest](https://github.com/dataeducator/student_academic_success/assets/107881738/3da114f1-886a-4ef5-8fa5-eede918ef429)
![Evaluate Decision Trees](https://github.com/dataeducator/student_academic_success/assets/107881738/cec50f9c-dada-4239-811e-3b3f07b21033)
![Confusion Matrix KNN](https://github.com/dataeducator/student_academic_success/assets/107881738/f944f1c3-e477-4e6f-a661-cb004c161b89)
![Confusion Matrix Support Vector Machine](https://github.com/dataeducator/student_academic_success/assets/107881738/9a0dc08f-794a-4766-8575-b22022314993)


The <code>analyze_feature_importances</code> function analyzes feature importances for the RandomForestClassifier and stores them in a data frame. The calculate_best_scores method uses GridSearchCV to find the best hyperparameters for each model based on a specified scoring metric. Finally, the identify_best_parameters function identifies the best hyperparameters and their corresponding recall scores for each model.

### iNterpret
Our code displays a confusion matrix, the most pertinent features, and their corresponding feature importances for each model. If a model does not have feature importances, the code alerts the user accordingly.

* The top 5 feature importances are identified and displayed for various models (Random Forest, SVM, Decision Trees, K Nearest neighbors), with a notification for models without feature importances.
* The random forest is the most performative model with a recall score of __0.76__
* The confusion matrix for random forest suggests that our predicts student dropouts and graduates much better than it predicts students who are enrolled: 
  - Dropout as Dropout prediction: correct 76 out of 100 times
  - Graduate as Graduate prediction: correct 93 out of 100 times
  - Enrolled as Enrolled prediction: correct 30 out of 100 times
  - Enrolled as Dropout prediction: correct 26 out of 100 times
  - Graduated as Dropout prediction: correct 3 out of 100 times

Top 5 Coefficients for Logistic Regression:
- Curricular units 2nd sem (approved): 1.4406130311414413
- Curricular units 2nd sem (enrolled): 0.9379467613448992
- Curricular units 1st sem (approved): 0.9284216462299857
- Tuition fees up to date: 0.5393465430753019
- Curricular units 2nd sem (grade): 0.479125037413678

Top 5 Feature Importances for Random Forest:
- Curricular units 2nd sem (approved): 0.14406489952064935
- Curricular units 2nd sem (grade): 0.10700750571270168
- Curricular units 1st sem (approved): 0.08976883790921418
- Curricular units 1st sem (grade): 0.0708387823689776
- Admission grade: 0.042196997614266894

Support Vector Machine model does not have feature importances.
- Top 5 Feature Importances for Decision Trees:
- Curricular units 2nd sem (approved): 0.7340676173420965
- Tuition fees up to date: 0.08683122950372858
- Curricular units 2nd sem (enrolled): 0.06661136590598447
- Curricular units 1st sem (evaluations): 0.021620120640126576
- Age at enrollment: 0.015020568606347337
***
## Conclusion
The feature importances from the Random Forest model and the coefficients from the Logistic Regression model both highlight the significant role of curricular units in the 2nd semester in predicting academic failure. Students with more approved units in the 2nd semester demonstrate a higher likelihood of academic success. To effectively reduce the academic failure rate, the student success team from the Instituto Politécnico de Portalegre should focus on supporting and guiding students to pass more units in the 2nd semester.

The Logistic Regression model emphasizes the importance of being up-to-date with tuition fees as a crucial factor in predicting academic success. Although it may not be among the top 5 feature importances for Random Forest, timely tuition fee payments are still relevant. To mitigate academic failure, the student success team should implement strategies to ensure students stay on top of their tuition fee payments, such as providing clear payment reminders and offering financial assistance when needed.

Both models underscore the significance of performance-related features, including grades and evaluations in the 1st and 2nd semesters. Students who excel in these evaluations demonstrate a higher likelihood of academic success. To reduce academic failure, the student success team should closely monitor early academic performance and provide additional support or interventions to students struggling in their evaluations or obtaining low grades.

In light of these insights, I recommend the student success team from the Instituto Politécnico de Portalegre adopt a multifaceted approach. By combining academic support, monitoring tuition fee payments, and providing early interventions based on performance, the team can effectively promote student success and improve overall student outcomes. Leveraging data-driven insights, the student success team can tailor their efforts and allocate resources strategically to support students better and foster a culture of academic achievement.
## Insights
Based on the information from the confusion matrices and feature analysis, we recommend the following:

* Adopting a multifaceted strategy that includes academic support and interventions.
* Monitoring tuition fee payments to mitigate academic failure.
* Providing early interventions between 1st and 2nd semester.

### Insight 1: Curricular Units in 2nd Semester Matter
Focusing on students' progress and success in their 2nd-semester curricular units can significantly contribute to reducing the rate of academic failure.

### Insight 2: Monitoring Tuition Fee Payments is Pivotal
By closely monitoring and supporting students to stay on track with tuition fee payments, institutions can foster an environment that reduces the rate of academic failure.

### Insight 3: Evaluations and Grades are Crucial
Prioritizing academic support and intervention based on early evaluations and grades can effectively contribute to minimizing the rate of academic failure.


# Future Work
* Explore applying XGBoost, a powerful gradient boosting algorithm, to a ternary (3 class) classification model.s.
* Extending the analysis to include US universities may also provide valuable insights. 
* Identifying common factors influencing student success across diverse contexts is possible.

Please review my full analysis in [my Jupyter notebook](https://github.com/dataeducator/student_academic_success/blob/main/student_academic_success.ipynb) or ([my presentation](https://github.com/dataeducator/student_academic_success/blob/main/presentation.pdf)).
You may contact me __Tenicka Norwood__ at tenicka.norwood@gmail.com if you have additional questions.

# Repository Structure
***
<pre>
   .
   └──student_academic_success_project/
      ├── README.md                                            Overview for project reviewers  
      ├── student_academic_success.ipynb                       Documentation of Full Analysis in Jupyter Notebook
      ├── presentation.pdf                                         PDF version of Full Analysis shown in a slide deck
      ├── notebook.pdf                                             PDF version of Full Analysis shown in Jupyter notebook
      ├── Data/                                                Externally sourced data  
      ├── Images/                                              Includes images generated from Python code and sourced externally
      └── .gitignore                                           Specifies intentionally untracked files
 </pre>
