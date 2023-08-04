steps for project data mining 


1- import library pandas, matpotlib, numpy, seaborn, linearRegression,
train_test_split, mean_squared_error, r2_score, make_pipeline, ColumnTransformer, oneHotEncoder, DecisionTreeRegressor, HumanName

2- display data with read_csv

3- clean data : Ensure that there are no missing or duplicate or negative  values with duplicated() and isnull() function

4- make gender attribute : define a list of name to predict gender
and loop over each name and predict the gender with function HumanName
and add gender column, then convert gender column to numerical values

5-important information for analysis : ex : head(), describe(), info()

6- analysis of data : 
a-calculate mean of basebay  
b-max of overtimepay
c-person who take the most overtimepay
d-persons who take most overtime pay
e-Job title for one of the most employees that take overtime pays
f-Total Pay Benefits for one of the most employees that take overtime pays
g-Person who take the most Total Pay Benefits, Person who take the lowest Total Pay Benefits
h-The mean of each pay per year
i-Number of jobs with nunique()
j-Person who take the most other pay
k-The largest ten jobs in base pay(using groupby the median of basebay in jobtitle and take the most 10 with nlargest(10), then create a horizontal bar chart)
l-The smallest ten jobs in base pay(using groupby the median of basebay in jobtitle and take the most 10 with nsmallest(10))
m-The largest ten jobs in overtime Pay(using groupby the median of otherpay in jobtitle and take the most 10 with nlargest(10))
n-The largest ten jobs in Benefits(using groupby the median of benefit in jobtitle and take the most 10 with nlargest(10))
o-The largest ten jobs in total Pay(using groupby the median of total pay in jobtitle and take the most 10 with nlargest(10))
p-The largest ten jobs in total Pay benefits(using groupby the median of pay benefits in jobtitle and take the most 10 with nlargest(10))
q-The most ten jobs which have emolyees with value_counts()
r-Counting how many times that word 'officer' is in (job title) with 
function officeWordCount consist of if condition the jobtitle contains office return true else return false and sum all true condition to calculate the number of job that contains 'officer' word



7- visualization :
a- count number of crimes per category, create a pie
chart of the crime counts and create a scatterplot , creat a scatterplot for overtime pay with jobtitle
b- Showing that total pays values are very close in all years using FacetGrid
c- heat map for data with method heatmap()
d- most popular 30 jobs and their distrbutions with barplot 
e- Comparison Between all jobs in (Fire Dapartment ) ---> BasePay
using bar() fire department cotains {'Chief, Fire Department','Asst Chf of Dept (Fire Dept)','Firefighter'}
f- BasePay based on years (Firefighter Job)  : filter data where jobtitle = firefighter and count the employee name of filter and add column experiences = number of replicate the employee name and sort them 


8- Models For Predicted (linear regression) : 
a- corr() used to calculate the correlation between columns in a pandas DataFrame
b- Select the columns to use for the model is jobtitle and gender
c- Encode the JobTitle column using one-hot encoding\
d- Split the dataset into training and testing subsets
e- Create the linear regression model and fit it to the training data
f- Make predictions on the testing data using model.predict()
g- Evaluate the performance of the model using R-squared
h- Adding a diagonal line for reference
i- show the plot

9- Models For Predicted (tree decision)
a- Select input and target variables
b- Encode the JobTitle column using one-hot encoding
c- Split data into training and testing sets
d- Create decision tree regression model
e- Train the model on the training data
f- Make predictions on the testing data
g- Evaluate model performance using R-squared
h- Adding a diagonal line for reference
i- Show the plot


10- filter jobtitle == asst chf of dep and count the employee name of filter and add column experiences = number of replicate the employee name and sort them 



11- Models For Predicted (linear regression) : 
a- corr() used to calculate the correlation between columns in a pandas DataFrame
b- Select the columns to use for the model is jobtitle and gender
c- Encode the JobTitle column using one-hot encoding\
d- Split the dataset into training and testing subsets
e- Create the linear regression model and fit it to the training data
f- Make predictions on the testing data using model.predict()
g- Evaluate the performance of the model using R-squared
h- Adding a diagonal line for reference
i- show the plot

12- Models For Predicted (tree decision)
a- Select input and target variables
b- Encode the JobTitle column using one-hot encoding
c- Split data into training and testing sets
d- Create decision tree regression model
e- Train the model on the training data
f- Make predictions on the testing data
g- Evaluate model performance using R-squared
h- Adding a diagonal line for reference
i- Show the plot
