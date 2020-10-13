# Predict Your Salary in the Data Professional World 
View app here -> [Predict Your Salary](https://predictyoursalaryy.herokuapp.com/)

## Table of contents
* [Summary](#summary)
* [Technologies](#technologies)
* [Contributors](#contributors)
* [Motivation](#motivation)
* [Installation](#installation)
* [Data](#data)
* [Development](#development)

## Summary
An app that predicts salary for data professionals based on experience type and location. It also provides metrics for these jobs titles based on demographics and other factors. 

### Technologies
* Python: pandas, numpy, Flask, SKlearn 
* Javascript: interactions and D3 visualizations 
* Databases: AWS RDS, Postgres 11, pgAdmin 4
* Webpage Design: HTML, CSS, Bootstrap 
* Tableau 

### Contributors
* [Sandra Froonjian](https://www.linkedin.com/in/sandrafroonjian/) 
* [Katarzyna (Kasia) Kalemba](https://www.linkedin.com/in/katarzynakalemba/)
* [Solito Reyes III](https://www.linkedin.com/in/solitoreyesiii/) 
* [Adriana van de Guchte](https://www.linkedin.com/in/adriana-van-de-guchte-6096791a3/) 
* [Shrilekha Vijayakanthan](https://www.linkedin.com/in/shrilekha-vijayakanthan-1986601b/) 

## Motivation
We wanted to create a tool to see how our skills compare to the current industry standard. By using industry data, we creating a machine learning model that predicts how much money one can make based on the selected factors. Looking at the job titles, skills, years of experience, programming languages, databases and many other factors valued in the data professional world, we explored the potential salaries within this field and the expectations of knowing certain skills. We created visuals that further explored the differences of demographics in different job titles looking at data from all over the world. By using our page, you can estimate how much you can expect to earn with the current skills you have as well as compare your expertise to those in the field. For an extended development description, please visit our Development link on the [Heroku webpage](https://predictyoursalaryy.herokuapp.com/development). 

## Installation 
### Local: 
* Clone the repository 
* Create a conda enviornment: 'conda create -name <env_name> python 3.7 --file requirements.txt
* Run app.py 
* Access at local host

### Remote Access
* [Heroku](https://predictyoursalaryy.herokuapp.com/)

## Data 
### Dataset 1: Kaggle Survey: 
This data set was collected from 171 countries as a survey for a Kaggle Competition. The survey responders were data professionals who are currently working in the field. We used their responses for the visuals for salary, gender, country, age and multiple data tools that they use in their current jobs. 
[Kaggle](https://www.kaggle.com/c/kaggle-survey-2019)

### Dataset 2: Brent Ozar Data
This dataset was used to develop our machine learning model for the salary prediction. We used factors such as location, title, primary database use, management level, education and year experience to predict a salary for a data professional. 
[Brent Ozar](https://www.brentozar.com/archive/2019/01/the-2019-data-professional-salary-survey-results/)


## Development 
### Data Preparation
#### Cleaning Dataset 1 Kaggle Survey: 
* The original CSV file was loaded in Jupyter Notebook and consisted of 246 columns and 19718 rows and was narrowed down to 109 columns and 19718 rows. 
* A clean CSV was exported for the remaining work. 

#### Cleaning Dataset 2 Brent Ozar Data: 
* The original CSV file was loaded in Jupyter Notebook and consisted of 6893 rows and 29 columns and was narrowed down to 6893 rows and 17 columns. 
* A clean CSV was exported for the remaining work. 

### Visualizations 
#### Tableau 
* The cleaned CSV file 1 was loaded into Tableau Desktop. 
* The following visualizations were made based on factors affecting salary: gender, age, location, education level, certificates and computer science background were all analyzed for how they played a role in the salary amount. 
* We also compare what we learned in the bootcamp compared to the expectations of the field. 
* The final dashboard was published in Tableau Public and finally embedded into our html page.

#### D3 
* Word cloud of the recommended first language to learn was built using a d3 version 3 base code and expanded upon to filter out values and repopulate only on changing inputs. Bubble chart of tool and language use in industry was built using d3 version 5 and d3.force was used to build movement animation.

### Machine Learning 
* Our Scikit-Learn Model machine learning model involved using a RandomForestClassifier and feature importance to narrow down the features for our model. We selected 10 features for our model, which are, in order: country, primary database, years with this database, region, manage staff, education is computer related, years with this type of job, telecommute days per week, employment sector, and job title. Because most of these features are categorical, and the model needs them to be numerical, pd.get_dummies was then used to convert categories to binary.

* Because our output was numerical, we then trained and tested our model using: Linear Regression, Gradient Boosting Regressor, Lasso, Ridge and Elastic Net. 

* The best with the best fit was the Gradient Boosting Regressor, with an r2 value of 0.6.

### Natural Language Processing 
* To see if we have the skills employers are looking for in the data science profession, we decided to look from the employer vantage point by analyzing the data science jobs available on indeed.com. In this approach, we scraped job descriptions (Beautiful Soup) for all data science jobs available on indeed.com. We processed those job descriptions through a TSNE Visualizer in order to identify evident clusters within the dataset and ran a TF-IDF Vectorizer to see the most common words used in each cluster.

* We processed those job descriptions through a TSNE Visualizer in order to identify evident clusters within the dataset and ran a TF-IDF Vectorizer to see the most common words used in each cluster. All job descriptions were then loaded into a TF-IDF Vectorizer and WordClouds were generated for each cluster.

* For amusement, we will attempt to create a job summary utilizing all the job descriptions from the dataset. We will use ntlk to tokenize the data by applying the CountVectorizer (one-hot encoding) and TF-IDF transformer (adding weights to the encoding). We can than fit the data into a PCA (Principal Component Anlysis) model in an attempt to reduce the dimensionality of the data.

### Flask App 
* **/tools_data/** route focuses on the popularities of different technologies of the data world
* **/tools_data/jobtitle** does the same as the route above, except there is an added filter to it that allows the user to add a job title to the URL
* **/recommendations_data** provides a count on the most recommended technologies to start with as a data professional.
* **/recommendations_data/jobtitle** does the same as the route above, except there is an added filter to it that allows the user to add a job title to the URL
* **/education_data** provides a breakdown of the count of each education level of each job title and also provides the average salary of each job title
* **/country_region_data** provides a list of all the unique country names of the dataset and its corresponding region
* **/predictions** is the route where the user’s response from the form is sent to. Their response is then processed to fit the model, and a prediction is returned. That response is sent back to that page to be used with Jinja.
* The rest of the routes are just simple routes that render html pages.
 
### Webpage and Deployment
* The HTML page was built with Javascript, CSS and Bootstrap features. 
* Our story-telling focuses on the tools of the trade and how these relate to expected salaries in the field. 
* The cleaned CSVs were imported using pgAdmin. 
* We deployed our application on Heroku with AWS RDS as the backend database instead of using Heroku postgres DB which has limitation of 10K records. 





