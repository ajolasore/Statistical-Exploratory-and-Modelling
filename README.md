# Statistical-Exploratory-and-Modelling



# Estimation of the Obesity Levels Based on Eating Habits And Physical Condition. 
### By Adeyemi Joshua Olasore 

## 1. INTRODUCTION 
### 1.1 Background

The epidemic of obesity is nothing new. It has existed for centuries. The startling increase in frequency 
during the past few decades is the most recent development. Across the past half century, it has spread all 
over the globe. Countries that have been known for their low obesity rates are now seeing increases; 
China's rate of obesity rise has doubled in the last decade. 
The CDC claims that this has an impact on a country's health, economy, and military preparedness. One 
in three adults is overweight, putting them at increased risk for cardiovascular disease, type 2 diabetes, 
and several cancers. 
The problem of obesity, sadly, is not restricted to adults. In the United States, 17% of kids and teens are 
overweight. Despite this being far greater than in previous years, the rate does appear to be worsening. 
However, the risk for diabetes in children is increased by a factor of four, and children who are fat are 
more likely to remain obese into adulthood. 
The changes in our environment and way of life have occurred at the same time that obesity rates have 
risen. Many of our once-manual labours are now performed by machines, our diets and the methods by 
which they are produced have evolved, and our communities are organized to favour the private 
automobile over other forms of transportation. 
Obesity has become a worldwide epidemic, and if we want to stop it, we need to find ways to treat its 
underlying causes. Predicting the possibility of obesity based on some accessible and quantitative 
parameters is intriguing to me as an aspiring data scientist. 

### 1.2 Research Questions 
Furthermore, in order to arrive a sizable conclusion, this research would like to answer the following 
questions;

• What is the relationship between various eating habits and Obesity? 
• What is the relationship between various physical conditions and Obesity? 
• What are the significant differences in obesity observed among gender, smokers, connection to 
family history, etc.? 
• Can Obesity in terms of Body Mass Index (BMI) be predicted given selected parameters? 

### 1.3 Objectives 
1. To determine and visualize the relationship between eating habit, physical condition of people and 
their corresponding body mass index. 
2. To evaluate the effect of the categorical parameters on the body mass index using the different 
correlation tests. 
3. To determine whether the obtained numerical and categorical parameters predicts obesity in terms 
of body mass index using regression model and classification algorithms.

## 2.0 METHODOLOGY 
### 2.1 Data Collection and Source 
The data gives the estimation of obesity levels in people from the countries of Mexico, Peru and 
Colombia, with ages between 14 and 61 and diverse eating habits and physical condition. According to 
UCI, the data was primarily collected using a web platform with a survey where anonymous users 
answered each question, then the information was processed obtaining 17 attributes and 2111 records. 
These raw data and related information was obtained from the Center for Machine Learning and 
Intelligent System,  University of California, Irvine (UCI) Machine Learning Repository. 

### 2.2 Data Introduction 
The dataset includes eating habits attributes such as: Frequent consumption of high caloric food (FAVC), 
Frequency of consumption of vegetables (FCVC), Number of main meals (NCP), Consumption of food 
between meals (CAEC), Consumption of water daily (CH20), and Consumption of alcohol (CALC), as 
well as physical condition attributes such as: Calories consumption monitoring (SCC), Physical activity 
frequency (FAF), Time using technology (TUE), Means of Transportation (MTRANS). Furthermore, 
based on Equation (1) and information from WHO and Mexican Normativity, the class variable 
NObeyesdad was established with the values: Insufficient Weight, Normal Weight, Overweight Level I, 
Overweight Level II, Obesity Type I, Obesity Type II, and Obesity Type III. Because the data comprises 
both numerical and continuous data, it may be analyzed using classification and prediction algorithms. 

### 2.3 Data Preparation and Preprocessing 
The data was imported into the IDE using the numpy and  pandas library for the needed wrangling and 
cleaning. Although basic preprocessing has been primarily done on the dataset, there was need to further 
check for some discrepancies. 
Some of the task involved checking for missing data (is.null()), confirming of the data types (.info()), 
removal of unessential variables (.drop()), renaming of column names of attributes (.rename()), 
confirming the values of the categorical variables (.unique()), the determination of the Body Mass Index 
(BMI) which is the numerical dependent variable needed for the analysis, and finally evaluating the 
descriptive statistical summary for the measure of central tendency and visible outliers (.describe()).  

### 2.4. Data Analysis tools  
#### 2.4.1 Exploratory Data Analysis 
In order to execute full exploratory analysis of the dataset the matplotlib.pyplot  and seaborn libraries 
were imported. 
Univariate analysis were carried out using the frequency distribution plots, histplot, barplot and 
countplots. This helps to get summary of selected categorical variables and check for patterns in the data. 
Bivariate analysis were as well carried out using the boxplot, jointplot, regplot, and lineplot. These 
helped in understanding the form, strength and dependence  of the relationship between two selected 
variables. Multivariate Analysis was done by; using the FacetGrid to visualize the distribution of multiple variables, 
and generating the correlation among the numerical and categorical (using the pivot table function) 
variables and visualized on the heatmap and clustermap. 

#### 2.4.2 Normality Test  
The normality of the dependent variable was checked whether the sample data was drawn from a 
normally distributed population. This was actualized by importing the statsmodels library and performing 
the function qqplot as well as the Shapiro from the scipy library. 

#### 2.4.3 Correlation Test 
The linear correlation between the two numerical variables. Basically, the test was done between each 
independent numerical variable and the dependent variable (BMI). This helped to measure the strength 
and direction of the relationship between them. The pearsonr and spearmanr function from the scipy.stats 
library was used to execute this. 

#### 2.4.4. T -Test 
This statistical test were performed to carry out hypothesis testing and compare the mean of two-grouped 
categorical variables (Gender, family history, FAVC, SMOKE, SCC). This was executed using the 
researchpy library. 

#### 2.4.5 Anova Test 
For categorical variable with more than two groups, the anova test was performed to check if there is a 
significant difference in the mean values of the groups . This was done for the variables CAEC, CALC 
and MTRANS using the statsmodels.api library, followed by executing the functions ols and 
.stats.anova_lm.  The corresponding pvalues and F values were obtained.

### 2.5 Machine Learning 
Based on the data given, there are both categorical and numerical attributes which would permit to 
perform both regression and classification algorithms to predict the output of the dependent variables.  

#### 2.5.1 Regression Algorithm 
Regression model was generated by making the machine to learn the relationship between the numerical 
variable  against the output variables. The following steps were taken, namely; 
1. Splitting of the data into the X and Y variables.  
2. Splitting the variables into the train and test variable using the train_test_split function from 
the sklearn.model_selection library. 
3. Instantiating the model using the LinearRegression function from the sklearn.linear_model 
library 
4. Fitting the model using the LinearRegression.fit function. 
5. Generating the predictions by using the LinearRegression.predict function 
6. Calculating the residuals by subtracting the predictions from the tested dependent variable. 
7. Plotting the distribution of the residual to check the uniform distribution. 
8. Evaluating the metrics of the model suing the metrics function from the sklearn library 
9. Generating the coefficients and the other values of the model.

#### 2.5.2 Classification Algorithm 
The output variable is binned into classes based on the value of the Body Mass Index (BMI) obtained and 
this is being used as the categorical output. This would help to predict the probability of occurrence using 
a binary form. 
The following steps were taken, namely; 
1. The dataset was duplicated to avoid complications in computing using the .copy() function 
2. The numerical variables in the dataset were removed using the .drop() function 
3. The independent categorical variables were turn to binary by using the get_dummies function 
from the pandas library, whereas the dependent variable, being more than two classes, were turned 
to integers first using the LabelEncoder function from the sklearn.preprocessing library, followed 
by turning the integers into binaries using the OneHotEncoder function from the same 
sklearn.preprocessing library. 
4. Splitting of the data into the X and Y variables. The binaries of the independent variable were 
concatenated in dataframe together. Each of the classes of the dependent variable were indexed 
and trained and tested. 
5. Splitting the variables into the train and test variable using the train_test_split function from the 
sklearn.model_selection library. Each of the classes of the output variables were trained and 
tested. 
6. Instantiating the model using the LogisticRegression function from the sklearn.linear_model 
library 
7. Fitting the model using the LogisticRegression.fit function for each of the classes. 
8. Generating the predictions by using the LogiscticRegression.predict function 
9. Evaluating the tests of the model using the classification_report function from the 
sklearn.meterics library 
10. Generating the confusion_matrix for the tested dependent variables and the derived prediction. 
11. Visualized into heatmap to analyse the True Positive, True Negative, False Positive and the False 
Negative.
