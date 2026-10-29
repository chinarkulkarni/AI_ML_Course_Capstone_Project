# AI\_ML\_Course\_Capstone\_Project



This is a repository for the Capstone Project of the Berkeley Haas AI/ML Course



### 1\. Project Title: In what year will the world's population growth rate drop to zero, and what will the peak population be then? 

   * This application reads the data from world_population.csv and API_SP.POP.GROW_DS2_en_csv_v2_2594848.csv data files, performs data preparation, data cleanup, builds a variety of supervised regression learning models, and provides recommendations for the best model that predicts the year in the future when the growth rate becomes zero, as well as the projected maximum world population.

### 2\. Notebook link

* The link for the notebook file: https://github.com/chinarkulkarni/AI_ML_Course_Capstone_Project/blob/main/capstone_project.ipynb

### 3\. Data Overview:

* The spreadsheet data/world_population.csv comes from the World Population Analysis dataset by Hasib Al Muzdadid on Kaggle, and the data is originally made publicly available by the US Census Bureau.
* It provides a list of all the countries in the world and their demographics, including the population for the beginning of every decade, starting in 1960.
* The spreadsheet data/API_SP.POP.GROW_DS2_en_csv_v2_2594848.csv comes from the Population Growth by each country dataset by Mahmoud Gamil on Kaggle, and this data is also based on publicly available demographic data.
* It provides a list of all countries and their percent population growth for each year, from 1970 to 2023.

### 4\. Data Analysis methodology:

* The data is read, cleaned up, and analyzed using the Python libraries Pandas, Seaborn, and NumPy.
* The data from the two spreadsheets is merged to create the data used for modeling.
* Line graphs and bar graphs are used to observe the population trends for the top 10 countries, as well as for the world population.

### 5\. Data Modeling Techniques Used:

* Time Series Analysis
* Linear Regression
* Feature Engineering
* Ridge Regularization Technique 
* ARIMA Time Series Model
* Ensemble techniques 
* Deep Neural Networks 

### 6\. Here are the findings made during the data analysis:

* The Time Series Decomposition was not found to be useful in this case, since the population plot consisted only of a trend, without any seasonal component.
* The 2nd degree Feature Engineering model fitted directly on the world population data was used as a baseline model. 
* The nth degree Feature Engineering model fitted individually on each country, and aggregated for the world proved to be a better model in creating the expected bell curve for the world population in the future. However, it exhibited a higher mean squared error on the validation dataset. Here are the observations made based on this model.
  * A different degree of Feature Engineering model was used for each country, based on the GridSearchCV results. This showed that each country is currently at a different stage of population growth trajectory.
  * This model predicted that the population growth will reach zero (and subsequently go negative) in the year 2051.
  * The maximum population that the world will have in this year will be 8.903 Billion.
* The Ridge regularization technique was a useful addition to the Feature Engineering model and improved the accuracy of the models.
* The ARIMA Model was not found to be useful in determining the year of population maxima, because it mainly works well with linear trends in the time series data.
* The Deep Neural Network was found to be too resource-consuming for this modeling task.
* The **Ensemble Technique model** provided the **best results**, with the lowest MSE and MAPE errors, predicting that the world population will be at its highest in the year **2075**, and the population will reach **9.88 billion** before starting to go down.

