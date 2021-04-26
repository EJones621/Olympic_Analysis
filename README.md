<<<<<<< HEAD
# Olympic Analysis

## Team
The team consists of the following 4 members: Alex Glickman, Ethan Jones, Matt Ansaldi and Cecily Martin
=======
# Olympic_Analysis
matt test
>>>>>>> e8f10d18af31d88f069c962695de7562a4992b7a

## Selected Topic
An Olympic data analysis is being conducted on 120 years of Olympic history. Specifically, data on athletes and medal results will be analyzed from Athens 1896 to Rio 2016 to explore whether a country’s GDP, population size, life expectancy rate and child mortality rate have an impact on a country’s Olympic medal counts.

## Reason why we selected our topic
We're all interested in sports.

### Resources Utilized to Complete Analysis
* **Data Sources:** 
    * [120 Years of Olympic History: Athletes and Results](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results)
    * [GDP per Capita for Countries by Year]( https://docs.google.com/spreadsheets/d/10vHiHnBQre07TwX75vTc_H1lf-w5-hbe5mZH4ro6QNE/edit#gid=176703676)
    * [Population for Countries by Year](https://docs.google.com/spreadsheets/d/14_suWY8fCPEXV0MH7ZQMZ-KndzMVsSsA5HdR-7WqAC0/edit#gid=569008164)
    * [Life Expectancy for Countries by Year](https://docs.google.com/spreadsheets/d/11mulzUH3_cueq-V9D5KIlo9oHE9YYZrUSeVyCin7_rM/edit#gid=176703676)
    * [Child Mortality for Countries by Year](https://docs.google.com/spreadsheets/d/1Av7eps_zEK73-AdbFYEmtTrwFKlfruBYXdrnXAOFVpM/edit#gid=176703676)
* **Entity Relationship Diagram (ERD) Tool**: [Quick Database Diagrams](https://www.quickdatabasediagrams.com/)
* **Languages:** Python
* **Python Dependencies:** pymongo, scikit-learn, pandas, numpy, seaborn, matplotlib
* **Applications:** MongoDB
* **Tools:** MS Excel, Jupyter Notebook 

## Description of our data source
Data sources utilized were found via [Kaggle.com]( https://www.kaggle.com/) and [Gapminder.org](https://www.gapminder.org/). Gapminder combines data from a variety of sources. 
* Olympic Games dataset (athlete_events.csv and noc_regions.csv) were found on Kaggle, but the source of the data stems from [www.sports-reference.com](https://www.sports-reference.com/)
* GDP dataset was found on GapMinder, but the source of the data stems from The World Bank [World Development Indicators]( www.gapm.io/xwb171), [Maddison](https://www.rug.nl/ggdc/historicaldevelopment/maddison/releases/maddison-project-database-2018) and The IMF [source 1](https://www.imf.org/external/pubs/ft/weo/2019/01/weodata/index.aspx)
 and [source 2](https://www.imf.org/en/publications/weo).
* Population dataset was found on GapMinder, but the source of the data stems from the [UN-Population Division, World Population Prospects 2019](https://population.un.org/wpp/) and [Maddison](https://clio-infra.eu/Indicators/TotalPopulation.html)
* Life expectancy dataset was found on GapMinder, but the source of the data stems from the [United Nations Population Division , WPP2019](https://population.un.org/wpp/Download/Standard/Interpolated/) and [IMHE](http://ghdx.healthdata.org/gbd-results-tool).
* Child Mortality dataset was found on GapMinder, but the source of the data stems from the [United Nations IGME, Child Mortality estimates,2018]( https://childmortality.org) and [United Nations POP, World Population Prospects 2019]( https://population.un.org/wpp/Download/Standard/Interpolated/)


## Questions we hope to answer with the data
* Is there a correlation between GDP and medal count?
* How important is the country’s population in terms of winning medals?
* Which parameter plays the biggest part when it is tested on its own?
* Does a country’s change in GDP over time, have an impact?  
* Which countries won the most medals over time?
* How many medals are forecasted to be won at upcoming Games (Tokyo 2020 / Beijing 2022)?  
* What are the GDP forecasts for years with upcoming Games (Tokyo 2020 / Beijing 2022)? 
* Which countries are expected to lead the medal tally?
* Do Olympic host countries win more medals?
* Does seasonality (winter / summer) have an effect?
* What is the mean age of athletes?
* Does athlete age / gender have an effect?
* Are there other factors that could impact Olympic medal counts?
* How have the Olympic Games evolved over time by looking at the participation of different nations, sports and events?  

## Description of the communication protocols
* A Trello board has been setup, with alerts for all deliverables. The board will be updated on an ongoing basis.
* Team communicates daily via Slack 
* Team meets via Google Meet, outside of scheduled 2-hour class sessions, twice per week and attends office hours. See calendar. 
* A [Google Drive](https://docs.google.com/presentation/d/1g6Cg4SvWYDNTRkjbSeMNEJljCG4KkJVyDHuyGzypul8/edit?usp=sharing) is utilized for storing meeting notes, datasets and other files which enable collaboration.
* Each team member has an individual branch on the GitHub project repository.


## Database
A provisional database was created in MongoDB. Lines 3 - 5 within the [cleaning_machine_learning.ipynb](https://github.com/cmmgw/Olympic_Analysis/blob/main/Import%20to%20MongoDB/cleaning_machine_learning.ipynb) Jupyter Notebook connect to the database, upload data to the database and shows data being taken off of the database. 

This ERD highlights the flow of information from one table, or CSV file, to another and captures the primary keys, foreign keys and data types for each column, within the corresponding CSV file.

![DBERD.png](https://github.com/cmmgw/Olympic_Analysis/blob/main/DBERD.png)

## Machine Learning Model
A machine learning model mockup was created, which takes in data from the provisional database, with the intent to predict the medal count by country based on GDP and population size. The output labels were the medals. See [cleaning_machine_learning.ipynb](https://github.com/cmmgw/Olympic_Analysis/blob/main/Import%20to%20MongoDB/cleaning_machine_learning.ipynb) Jupyter Notebook.

A supervised learning model was selected because it captures non-binary non-classifiers. We are training model by selecting data, preprocessing it, and using a random forest regression model to predict outcomes. The model’s accuracy is based on the Root Mean Squared Error (RMSE) of 24.70%. The RMSE is the standard deviation of the residuals where the residuals are the prediction errors. Lower values indicate better fit. The model works by getting input data, scaling it with the standard scaler and using random forest to train the model.


=======