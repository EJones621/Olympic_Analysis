# Olympic Analysis

## Team
The team consists of the following 4 members: Alex Glickman, Ethan Jones, Matt Ansaldi and Cecily Martin

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

This ERD highlights the flow of information from one table, or CSV file, to another and captures the primary keys, foreign keys, and data types for each column, within the corresponding CSV file.

![DBERD.png](https://github.com/cmmgw/Olympic_Analysis/blob/main/DBERD.png)

## Machine Learning Model
Before the data was fed into the machine learning model, it was preprocessed. The first and most time consuming step was to merge the datasets. The most common column to merge on was the column containing the country name. This is where most of the cleaning was done as names such as St. Lucia verus Saint Lucia wouldn't be found as a match. The majority of this type of cleaning was done manually in Excel since writing lines of code for each country name that didn't match would've been even more time consuming.

Once the cleaning was done, it was time to add the code for the machine learning model. The machine learning model we chose was random forest. This decision came from the fact that our data is labeled (points to supervised machine learning) and that our output (medal count) is numerical. Random forests are made up of many decision trees (a decision tree can be thought of as a collection of if else statements). Each tree in the random forest makes its own prediction on the ouput. After this, the average of all the outputs is computed to give you the final result. That's to put it in simple terms!

According to the regressor.score function, our model has about 80% accuracy. The RMSE (root mean square error) is about 5. This means that the standard deviation of the residuals (prediction errors) is about 5 medals. Residuals measure how far from the regression line the actual data points are. That's pretty good for about a week worth of work.

See [cleaning_machine_learningV6.ipynb](https://github.com/cmmgw/Olympic_Analysis/blob/main/Notebooks/cleaning_machine_learningV6.ipynb) Jupyter Notebook.

=======

# Technologies Used
## Data Cleaning and Analysis
***Pandas*** will be used to clean the data and perform an exploratory analysis. Further analysis will be completed using ***Python***.

## Database Storage
The database we chose is MongoDB. Within our code, we connect to the database, upload the xlsx and csv files as separate collections, pull each collection off of the database, then turn each collection into a DataFrame. We've uploaded a file called password.py (added to the gitignore file) to GitHub that contains a variable that holds the connection string that allows each team member to access the data on the database.

## Machine Learning
***SciKitLearn*** is the Machine Learning library we'll be using to create a classifier. The train-test-split function from the SciKitLearn library is used to setup our training and testing. Random Forest Regression was used to complete the training.

## Dashboard
Our fully functioning and interactive dashboard will be hosted on ***Tableau*** or by utilizing a Flask template which would integrate ***D3.js***. However, at this time we are unsure which one will be best suited for the presentation of analysis.
