<h1 align="center">Regression Analysis: Seoul Bike Sharing Demand Dataset</h1>

<h2>📖 Overview</h2>

For this project my proposal is to solve the problem of forecasting the hourly demand of
rental bikes by using historical demand data. In recent years, within many urban cities, there
has been a prevalence of improvements in modes of transportation to ensure that people have
many methods to easily exercise and commute (V E, Park, & Cho, 2020b). Ensuring that rental
bike services have a proper supply of bikes available at the right time for the public helps
decrease wait times (V E, Park, & Cho, 2020b). This inherently reduces the risks of financial
losses for the company, customer complaints, and poor service reviews. The aim of my project
is to predict the number of required rental bikes each hour to ensure that a proper supply of
rental bikes is present.

The theme I have chosen for this project is Regression. Regression analysis will be used
to compute the dependent variable, Rented Bike Count, based on the given independent
variables. Furthermore, predictive models will be built with the goal of minimizing error and
maximizing accuracy for the predictions. The following research questions will be examined.
What are the attribute types (nominal, ordinal, or quantitative) in the dataset? Are there any
missing values or outliers in the dataset? What are the means, minimums, maximums, and
standard deviations of the attributes? Using histograms, what does the distribution of numeric
attributes look like? Which attributes seem to be correlated? Which attributes may be included
or eliminated from the models?

The dataset that I am proposing to use for this project is the Seoul Bike Sharing Demand
Dataset, https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand, from the UCI
Machine Learning Repository (V E, Park, & Cho, 2020b). It has 8,760 rows, 14 attributes, and in
particular, the Rented Bike Count attribute which represents the count of rental bikes that are
rented at each hour (V E, Park, & Cho, 2020b). The dataset also contains weather information such as Temperature (°C), Humidity (%), Wind Speed (m/s), Visibility (10m), Dew Point
Temperature (°C), Solar Radiation (MJ/m2), Rainfall (mm), Snowfall (cm), and Seasons (V E,
Park, & Cho, 2020b). There are also attributes related to date and time which are Date, Hour,
Holiday, and Functioning Day (V E, Park, & Cho, 2020b).

The tools that I am proposing to use are Python and Tableau. The techniques that I am
proposing to use to solve the stated problem are linear regression, regression trees, and kNN
regression. I am proposing to build these regression models using all attributes which I will
consider as baseline models and compare them with regression models that I will build with only
selected features that are deemed statistically significant. In terms of variable selection, I am
proposing to use either forward selection, backward elimination, or stepwise regression. These
baseline and selected features models will be used to compare each prediction’s accuracy to
showcase how they may change due to the inclusion/elimination of attributes. Given the aim of
this project, the desired metric for optimization is accuracy, namely the ability for my models to
predict a stable number of rental bikes at each hour.

<h2>📑Background</h2>

In recent years it has been claimed that there are very few research
articles related to forecasting demand of bike rentals using regression analysis. As this type of
transportation grows around the world and new bike rental companies are formed, it will become
paramount for these types of machine learning studies to ensure that supplies of bikes are at
adequate levels and to ultimately reduce financial losses. Although there are research articles
available using many machine learning methods, some being simple, and some being very
advanced, there does not seem to be research done specifically to highlight the importance of
variable selection. This is where my research is different in that one of the goals is to showcase
how variable selection may significantly impact regression models and their performance. The
research that I will complete as well aims to provide an elementary appreciation of machine
learning and hopes to enlighten many students to appreciate, understand, and improve for
future research studies.

<h2>🧭 Navigation</h2>

In terms of navigating this repository, I have separated my source code and files into different directories.

**1. data_visualization**

- Contains compilation of miscellaneous data visualizations used for my written reports

**2. dataset**

- Contains the working dataset as a .csv flat file and a pandas profiling report used for exploratory data analysis

**3. initial_results_code**

- Contains all source code and files related to the Initial Results and the Code module for assessment

**4. tableau**

- Contains all files used by and generated from Tableau

<h2>💻 Initial Results and Code</h2>

The initial_results_code directory in this repository contains source code and files that were created for the purposes of the following categories:

Note: A compilation of the uploaded technical reports for this section can be found in the PDF compilation_technical_reports.pdf.

**1. Data Preparation**

File name: data_preparation.ipynb

Note: The following is an excerpt from this Jupyter Notebook to provide a general idea of the steps taken for data preparation.

For the SeoulBikeData.csv dataset, I will convert the categorical attributes to quantitative attributes such that they are in a valid format for use in building the regression models.

For this dataset, the categorical variables which I will transform are Date, Seasons, Holiday, and Functioning Day.

First, for the Date attribute, I will transform it to get the Day, Month, and Year as these 3 new attributes will be quantitative.

Second, for the Seasons attribute, I will use one hot encoding to create 4 new binary attributes to represent each Seasons value. This is because the Seasons attribute is not ordinal hence one hot encoding is a suitable method to ensure the 4 new attributes are valid for regression model building.

Third, I will focus on transforming the Holiday and Functioning Day attributes to binary quantitative attributes. Specifically, for the Holiday attribute, if the record in our dataset is "No Holiday" then it will be mapped as 0 and if it is "Holiday" then it will be mapped as 1.

Finally, I have completed data preparation and will now convert the dataframe containing the Seoul Bike data into a .csv flat file for the next step which is predictive modeling.

**2. Pandas Profiling Report**

File name: pandas_profiling_report.html

The pandas-profiling module was used to generate this report for exploratory data analysis. It provides analysis of the seoul_bike_data_prepared.csv dataset. This includes an overview of many exploratory data analysis elements such as viewing the head and tail of the dataset records, pandas column data types, descriptive statistics, graphs, and correlation.

Note: This pandas profiling report provides insights and data visualizations on the new prepared dataset generated from the data_preparation.ipynb.

**3. Baseline Models**

File name: baseline_models.ipynb

This Jupyter Notebook contains the 3 regression models using all attributes of the prepared dataset (seoul_bike_data_prepared.csv). Namely, linear regression, regression tree, and k-nearest neighbours. Since all attributes of the dataset will be used in the regression analyses, I have therefore named these as baseline models. 10-fold cross validation will be used.

The intent is to compare these baseline models with selected features models in terms of model performance. Selected features models in this case means regression models that I will build with only attributes that are deemed statistically significant.

**4. Selected Features Models**

File name: selected_features_models.ipynb

This Jupyter Notebook contains the 3 regression models using selected features of the prepared dataset (seoul_bike_data_prepared.csv). Namely, linear regression, regression tree, and k-nearest neighbours. Since select features of the dataset will be used in the regression analyses, I have therefore named these as selected features models. 10-fold cross validation will be used.

The intent is to compare these selected features models with the baseline models in terms of model performance. Selected features models in this case means regression models that I will build with only attributes that are deemed statistically significant.

<h2>📜 References</h2>

Feng, Y. L., & Wang, S. S. (2017, June 29). A forecast for bicycle rental demand based on
random forests and multiple linear regression. IEEE Xplore. Retrieved February 16, 2023,
from https://ieeexplore.ieee.org/abstract/document/7959977

Kang, Z., Zuo, Y., Huang, Z., Zhou, F., & Chen, P. (2018, January 11). Research on the
Forecast of Shared Bicycle Rental Demand Based on Spark Machine Learning
Framework. IEEE Xplore. Retrieved February 16, 2023, from
https://ieeexplore.ieee.org/abstract/document/8253072

Gao, C., & Chen, Y. (2022, January 7). Using machine learning methods to predict demand for
bike sharing. SpringerLink. Retrieved February 16, 2023, from
https://link.springer.com/chapter/10.1007/978-3-030-94751-4_25

Qi, X., Gao, Y., Li, Y., & Li, M. (2022, March 15). K-nearest Neighbors Regressor for Traffic
Prediction of Rental Bikes. IEEE Xplore. Retrieved February 16, 2023, from
https://ieeexplore.ieee.org/abstract/document/9730527

V E, S., Park, J., & Cho, Y. (2020a, February 6). Using data mining techniques for bike sharing
demand prediction in Metropolitan City. Computer Communications. Retrieved February
16, 2023, from https://www.sciencedirect.com/science/article/pii/S0140366419318997

V E, S., & Cho, Y. (2020a, February 13). A rule-based model for Seoul bike sharing demand
prediction using weather data. Taylor & Francis. Retrieved February 16, 2023, from
https://www.tandfonline.com/doi/full/10.1080/22797254.2020.1725789

V E, S., & Cho, Y. (2020b, February 26). Season wise bike sharing demand analysis using
random forest algorithm. Wiley Online Library. Retrieved February 16, 2023, from
https://doi-org.ezproxy.lib.torontomu.ca/10.1111/coin.12287

V E, S., Park, J., & Cho, Y. (2020b, March 1). Seoul Bike Sharing Demand Data Set. UCI
Machine Learning Repository: Seoul Bike Sharing Demand Data Set. Retrieved February
16, 2023, from https://archive.ics.uci.edu/ml/datasets/Seoul+Bike+Sharing+Demand
