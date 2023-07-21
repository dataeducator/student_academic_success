# Student Academic Success Classification Analysis
***
![md-duran-1VqHRwxcCCw-unsplash](https://github.com/dataeducator/student_academic_success/assets/107881738/7ceeaca1-99f5-41fd-bbf6-9b0b1458d47b)

# Business Understanding:
* __Stakeholder__: Instituto Politecnico de Portalegre
* __Business Case__: I am a new data scientist and have joined the challenge the Instituto Politecnico de Portalegre created to classify students' academic success. Researchers at the Instituto Politecnico de Portalegre want to reduce the rate of student academic failure in higher education.

# Overview
In this case, the goal is to craft and refine a reliable model by using machine learning techniques to identify which students are at risk at earlier stages of their academic path to put strategies to support students in place to mitigate their likelihood of dropping out of higher education. While the model was trained and tested with data from higher education students in Portugal, the lag in academic success within higher education is also a challenge within the United States. Colleges and Universities face the ever-pressing challenge of identifying students who are at risk of not graduating on time and providing effective interventions to move those students back onto a positive pathway to graduation.
> The completion rates of (US) undergraduates within six years of enrollment stand at only __62.3%__ as of 2022.
>
> -- Hanneh Bareham and Chelsea Wing (bankrate.com)
>
> 

Carnevale et al. (2021) Georgetown University in their study highlighted the substantial disparity in lifetime earnings based on educational attainment. In particular, the gist of this study showed that an average person with only a high school diploma or GED would earn an estimated __1.6 million dollars in their lifetime__, compared to a person with a bachelor's degree who potentially can make __~2.8 million dollars__. This profound disparity in earning potential underscores the transformative power of higher education and highlights the significance of timely graduation in enhancing students' long-term financial security.

# Data Understanding and Analysis
***
In this project, I will use the OSEMiN pipeline to:

* Obtain → Import the data.
* Scrub → Manage the datatypes, and resolve missing data or duplicates.
* Explore → Identify patterns within the relationships between variables in the data.
* Model → Create a set of predictive models.
* iNterpret → Identify insights and create visualizations of findings.

## Source of Data
The University of California (Irvine) hosts a machine learning repository with datasets that can be evaluated using machine learning techniques. The dataset used in this exploration can be found [here](https://archive.ics.uci.edu/dataset/697/predict+students+dropout+and+academic+success). This dataset was created as a part of a project to reduce academic dropout and failure rates in higher education by leveraging machine learning to identify at-risk students early in their academic careers and provide them support to improve their likelihood of on-time graduation.  


## Description of Data
***
The data can be found in the data folder of this repository includes information that is known from the time a student enrolls until their second semester of enrollment, including their:
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

The data was preprocessed to address missing values and anomalies. I am going to use a minimum of 4 machine-learning algorithms to classify this data and will also use exploration to determine the following guiding questions:

- How does marital status influence the likelihood of students graduating on time?
- Does the timely payment of tuition fees have any impact on the graduation status of students?
- Is there a relationship between the parents' qualifications and the graduation status of students?
In order to determine answers to my guiding questions, first, I needed to import relevant libraries and packages.

* <code>pandas</code>: a data analysis and manipulation library which allows for flexible reading, writing, and reshaping of data
* <code>numpy</code>: a key library that brings the computational power of languages like C to Python
* <code>matplotlib</code>: a comprehensive visualization library
* <code>seaborn</code>: a data visualization library based on matplotlib
* <code>statsmodels</code>: a library used to understand statistical relationships between variables, often used in the field of economics.
* <code>sklearn</code>: a machine learning library for data processing and modeling.

## Modeling

### Obtain
The <code> ObtainData </code>class defines a constructor to initialize the data_path attribute and set data to None. It provides a method <code>load_data</code> to load the dataset from the specified data_path using pandas, assuming the dataset is in .csv format with semicolons as the separator, and assigns the loaded data to the data attribute. 
The <code>obtain_data</code> method calls the <code>load_data</code> method and returns the loaded dataset.

### Scrub
The <code>ScrubData</code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides a method check_placeholders to identify the presence of placeholders *(e.g., '?', '#', 'NaN', 'null', 'N/A', '-')* throughout the entire DataFrame. If any placeholders are found, they are replaced; otherwise, a message indicating that no placeholders were detected is printed.

Additionally, the class includes a <code>clean</code> method to perform data-cleaning operations. In this method, rows containing missing data are removed using  <code>dropna</code> function and the resulting cleaned DataFrame is returned.

### Explore
The <code>ExploreData </code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides methods for examining the structure of the dataset, checking and dropping duplicates, generating and displaying a correlation matrix heatmap, plotting a pair plot, and filtering a correlation table based on specified thresholds. Additionally, the class includes methods for plotting the gender distribution, dropout distribution by gender, and the target variable distribution for college students in the dataset. These visualizations aid in exploring and understanding the dataset's characteristics and relationships between variables.

The <code>AnalyzeData</code> class defines a constructor to initialize the data attribute with a pandas DataFrame. It provides the <code>analyzedata</code> method to perform data analysis and generate various bar charts and boxplots to examine the influence of different features on graduation status. The class includes methods to map and revise variable values, filter relevant columns, and plot bar charts and boxplots using Seaborn and Matplotlib. The visualizations aim to gain insights into how various factors such as age range, curricular units, tuition fees, scholarship status, and previous qualification impact graduation status. The different visualizations facilitate the exploration of potential patterns and relationships in the data to support decision-making and interventions for improving graduation rates at Instituto Politecnico de Portalegre.

###  Question 1:How does the number of credits students enrolled in each semester influence the likelihood of students graduating on time??
***
For the first question, I looked for correlations between the graduation status of students and the enrollment patterns of students each semester.  

### Visualization for Question 1

<img width="514" alt="EDA for Question 1a" src="https://github.com/dataeducator/student_academic_success/assets/107881738/df8596b8-ae17-4cda-925c-285e741d13d1">

<img width="508" alt="EDA for Question 1b" src="https://github.com/dataeducator/student_academic_success/assets/107881738/0453827a-316d-4b22-a5b9-48cf596d1435">

### Question 2: Does the timely payment of tuition fees have any impact on the graduation status of students??
***
For the second question, I looked at tuition fee payments for each of the three classes.

### Visualization for Question 2
<img width="476" alt="EDA for Question 2" src="https://github.com/dataeducator/student_academic_success/assets/107881738/efe9f06b-62d6-45b2-b509-8bcb9a9a7127">


### Question 3: Is there a relationship between the age a student is at enrollment and the graduation status of students?
***
For the third question, I looked at looked for correlations between the age a student was at enrollment and their graduation status, along with visualizations created with <code>seaborn</code> and <code>matplotlib</code>

### Visualization for Question 3

<img width="484" alt="EDA for Question 3" src="https://github.com/dataeducator/student_academic_success/assets/107881738/26970cc4-0009-4d72-a808-7d78411f7a34">

### Model
The TernaryClassifier is a class designed to perform classification tasks on datasets with a ternary (three-class) target variable. It provides methods for data preprocessing, training multiple classification models, making predictions, and tuning hyperparameters to optimize model performance.

The name "TernaryClassifier" is derived from the term "ternary," which refers to systems or situations that involve three elements or options. In the context of classification, a ternary classification problem involves predicting one of three possible classes or categories for each data instance.

Overview of the TernaryClassifier class:

* Constructor: The class constructor takes a pandas DataFrame (data) as input and initializes the object. The input data frame should contain the features (X) and the ternary target variable (y) that the classifier will predict.

* Preprocessing: The <code>preprocess_data()</code> method separates the features (X) and the target variable (y) from the input DataFrame. It then scales the feature data using StandardScaler and encodes the target variable using LabelEncoder. The scaled feature data is converted back to a DataFrame with appropriate column names and returned.

* Model Library: The class defines a library of classification models that can be used for training. The library includes models like <code> {Logistic Regression, K-Nearest Neighbors, Support Vector Machine, Decision Trees, and Random Forests}</code>.

* Training: The <code>train_model()</code> method trains each model in the library on the preprocessed data (X and y). It fits the models to the training data, making them ready for prediction.

* Prediction: The <code>predict()</code>method takes testing feature data (X_test) and predicts the target variable values using all the trained models. The method returns a dictionary containing the predictions of each model.

* Hyperparameter Tuning: The class includes a <code>tune_parameters()</code> method, which can be used to tune hyperparameters for a specific classifier using GridSearchCV. This method helps optimize model performance by finding the best hyperparameters for each model.

* Training with Parameter Tuning: The <code>train_model_with_parameter_tuning()</code> method trains the classification models with their hyperparameters tuned using GridSearchCV. This method iterates through each model, performs hyperparameter tuning, and returns a dictionary of the best models with their tuned hyperparameters. Additionally, it identifies the most performative model based on the recall score.

Each of the models was trained using an 80/20 split and then evaluated using recall:

### Evaluation
I created a <code>ModelEvaluation </code> class to evaluate different classifier models for a ternary classification problem. The class contains methods to calculate evaluation metrics such as accuracy, precision, recall, and F1 score for each trained model. It also includes functions to analyze feature importances for the RandomForestClassifier and identify the best hyperparameters that yield the best recall score for each model using cross-validation.

The evaluate_models method takes a trained TernaryClassifier instance, performs predictions on the test data, and calculates various evaluation metrics for each model. The analyze_feature_importances function analyzes feature importances for the RandomForestClassifier and stores them in a data frame. The calculate_best_scores method uses GridSearchCV to find the best hyperparameters for each model based on a specified scoring metric. Finally, the identify_best_parameters function identifies the best hyperparameters and their corresponding recall scores for each model.


<img width="238" alt="ModelEvaluation" src="https://github.com/dataeducator/student_academic_success/assets/107881738/64d9ed1c-29ca-4980-96b2-d95282ebe9e3">

### iNterpret
While the random forest is the most performative model with a recall score of __0.76__, we also need a way to retrieve and display the top coefficients or feature importances for each of the models if they are available. With this in mind, we calculated the absolute values of the coefficients for logistic regression and sorted them in descending order to show the most influential features in predicting the target variable. If the Logistic Regression model does not have coefficients, it notifies the user that they are unavailable. Afterward, we identify the top 5 feature importances for models such as Random Forest, Support Vector Machines, Decision Trees, and K-Nearest Neighbors. Our code displays the most important features and their corresponding importance for each model. In case a model does not have feature importances, the code alerts the user accordingly.

Top 5 Coefficients for Logistic Regression:
Curricular units 2nd sem (approved): 1.4406130311414413
Curricular units 2nd sem (enrolled): 0.9379467613448992
Curricular units 1st sem (approved): 0.9284216462299857
Tuition fees up to date: 0.5393465430753019
Curricular units 2nd sem (grade): 0.479125037413678

Top 5 Feature Importances for Random Forest:
Curricular units 2nd sem (approved): 0.14406489952064935
Curricular units 2nd sem (grade): 0.10700750571270168
Curricular units 1st sem (approved): 0.08976883790921418
Curricular units 1st sem (grade): 0.0708387823689776
Admission grade: 0.042196997614266894

Support Vector Machine model does not have feature importances.
Top 5 Feature Importances for Decision Trees:
Curricular units 2nd sem (approved): 0.7340676173420965
Tuition fees up to date: 0.08683122950372858
Curricular units 2nd sem (enrolled): 0.06661136590598447
Curricular units 1st sem (evaluations): 0.021620120640126576
Age at enrollment: 0.015020568606347337
***
## Conclusion
The feature importances from the Random Forest model and the coefficients from the Logistic Regression model both highlight the significant role of curricular units in the 2nd semester in predicting academic failure. Students who have more approved units in the 2nd semester demonstrate a higher likelihood of academic success. To effectively reduce the rate of academic failure, the student success team from the Instituto Politécnico de Portalegre should focus on supporting and guiding students to pass more units in the 2nd semester.

The Logistic Regression model emphasizes the importance of being up-to-date with tuition fees as a crucial factor in predicting academic success. Although it may not be among the top 5 feature importances for Random Forest, timely tuition fee payments are still relevant. To mitigate academic failure, the student success team should implement strategies to ensure students stay on top of their tuition fee payments, such as providing clear payment reminders and offering financial assistance when needed.

Both models underscore the significance of performance-related features, including grades and evaluations in the 1st and 2nd semesters. Students who excel in these evaluations demonstrate a higher likelihood of academic success. To reduce academic failure, the student success team should closely monitor early academic performance and provide additional support or interventions to students who may be struggling in their evaluations or obtaining low grades.

In light of these insights, I recommend the student success team from the Instituto Politécnico de Portalegre adopt a multifaceted approach. By combining academic support, monitoring tuition fee payments, and providing early interventions based on performance, the team can effectively promote student success and improve overall student outcomes. Leveraging data-driven insights, the student success team can tailor their efforts and allocate resources strategically to support students better and foster a culture of academic achievement.
## Insights
### Insight 1: Curricular Units in 2nd Semester Matter
Focusing on students' progress and success in their 2nd-semester curricular units can significantly contribute to reducing the rate of academic failure.

### Insight 2: Monitoring Tuition Fee Payments is Pivotal
By closely monitoring and supporting students to stay on track with tuition fee payments, institutions can foster an environment that reduces the rate of academic failure.

### Insight 3: Evaluations and Grades are Crucial
Prioritizing academic support and intervention based on early evaluations and grades can effectively contribute to minimizing the rate of academic failure.


# Future Work
* Explore how to apply XGBoost, a powerful gradient boosting algorithm, to a ternary (3 class) classification model.s.
* Extending the analysis to include US universities may also provide valuable insights. 
* Identifying common factors influencing student success across diverse contexts is possible.

Please review my full analysis in [my Jupyter notebook](https://github.com/dataeducator/student_academic_success/blob/main/student_academic_success.ipynb) or [my presentation](link to pdf of presentation).
You may reach out to __Tenicka Norwood__ at tenicka.norwood@gmail.com if you have additional questions.

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
