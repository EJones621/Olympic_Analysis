# Olympic Analysis

## Team
The team consists of the following 4 members: Alex Glickman, Ethan Jones, Matt Ansaldi and Cecily Martin

## Selected Topic
An Olympic data analysis is being conducted on 120 years of Olympic history. Specifically, data on athletes and medal results will be analyzed from Athens 1896 to Rio 2016 to explore whether a country’s GDP and population size have an impact on a country’s Olympic medal counts.

## Reason Why Topic was Selected
We're all interested in sports.

### Resources Utilized to Complete Analysis
* **Data Sources:** 
    * [120 Years of Olympic History: Athletes and Results](https://www.kaggle.com/heesoo37/120-years-of-olympic-history-athletes-and-results) (Datasets: [athlete_results.csv](https://docs.google.com/spreadsheets/d/1oq7ZiU0WXdj5uTG3e0RbO4XkvAJ93q1_klmR1wO1hXA/edit?usp=sharing) and [noc_regions.csv]( https://docs.google.com/spreadsheets/d/1B6UP6FGVwBZKtATKP-vEv1cYqiX71AQzeJbTOWhGP3U/edit?usp=sharing) )
    * [Olympic Games Hosts](https://www.kaggle.com/piterfm/olympic-games-hosts?select=olympic_hosts.csv) (Dataset: [olympic_hosts.csv]( https://docs.google.com/spreadsheets/d/19hH8YdfaiZHcgTKzv-7lgV_VsHequsHHP9oj0tbg6iI/edit?usp=sharing))
    * [GDP per Capita for Countries by Year]( https://docs.google.com/spreadsheets/d/10vHiHnBQre07TwX75vTc_H1lf-w5-hbe5mZH4ro6QNE/edit#gid=176703676)
    * [Population for Countries by Year](https://docs.google.com/spreadsheets/d/14_suWY8fCPEXV0MH7ZQMZ-KndzMVsSsA5HdR-7WqAC0/edit#gid=569008164)
    * [Latitude and Longitude for Every Country and State](https://www.kaggle.com/paultimothymooney/latitude-and-longitude-for-every-country-and-state) (Dataset: [world_country_and_usa_states_latitude_and_longitude_values.csv](https://docs.google.com/spreadsheets/d/1Ucg0qM9DdTBYx3fKQD4Ag3FfIYtH9tOtzRiP6UCJ2Mw/edit?usp=sharing))
* **Entity Relationship Diagram (ERD) Tool**: [Quick Database Diagrams](https://www.quickdatabasediagrams.com/)
* **Languages:** Python
* **Python Dependencies:** pymongo, scikit-learn, pandas, numpy, seaborn, matplotlib, SciPy
* **Applications:** MongoDB, Tableau
* **Tools:** MS Excel, Jupyter Notebook 

## Description of Data Sources
Data sources utilized were found via [Kaggle.com]( https://www.kaggle.com/) and [Gapminder.org](https://www.gapminder.org/). Gapminder combines data from a variety of sources. 
* 120 Years of Olympic History: Athletes and Results dataset (athlete_events.csv and noc_regions.csv) were found on Kaggle, but the source of the data stems from [www.sports-reference.com](https://www.sports-reference.com/)
* Olympic Games Hosts dataset (Olympic_hosts.csv) was found on Kaggle, but the source of the data stems from [www.olympic.org](https://www.olympic.org)
* GDP dataset was found on GapMinder, but the source of the data stems from The World Bank [World Development Indicators]( www.gapm.io/xwb171), [Maddison](https://www.rug.nl/ggdc/historicaldevelopment/maddison/releases/maddison-project-database-2018) and The IMF [source 1](https://www.imf.org/external/pubs/ft/weo/2019/01/weodata/index.aspx)
 and [source 2](https://www.imf.org/en/publications/weo).
* Population dataset was found on GapMinder, but the source of the data stems from the [UN-Population Division, World Population Prospects 2019](https://population.un.org/wpp/) and [Maddison](https://clio-infra.eu/Indicators/TotalPopulation.html)
* Latitude and Longitude for Every Country and State dataset (world_country_and_usa_states_latitude_and_longitude_values.csv) was found on Kaggle and for the project’s analysis, the file was renamed to coordinates.csv in order to condense the naming convention. The data stems from [Google’s Dataset Publishing Language](https://developers.google.com/public-data/docs/canonical/countries_csv)

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

<<<<<<< HEAD
## Description of the communication protocols
* A Trello board has been setup, with alerts for all deliverables. The board will be updated on an ongoing basis.
* Team communicates daily via Slack 
* Team meets via Google Meet, outside of scheduled 2-hour class sessions, twice per week and attends office hours. See calendar. 
* A [Google Drive](https://drive.google.com/drive/folders/19HNRa2zpd1u6bmqXRbQOobYoCC_3iSnQ?usp=sharing) is utilized for storing meeting notes, datasets and other files which enable collaboration.
* Each team member has an individual branch on the GitHub project repository.

=======
>>>>>>> e16c4b8411938c9fb0bcd6339c0d76d582e22d45
## Database
A provisional database was created in MongoDB. Lines 3 - 5 within the [cleaning_machine_learning.ipynb](https://github.com/cmmgw/Olympic_Analysis/blob/main/Import%20to%20MongoDB/cleaning_machine_learning.ipynb) Jupyter Notebook connect to the database, upload data to the database and shows data being taken off of the database. 

This ERD highlights the flow of information from one table, or CSV file, to another and captures the primary keys, foreign keys, and data types for each column, within the corresponding CSV file.

![DBERD.png](https://github.com/cmmgw/Olympic_Analysis/blob/main/Graphics/DBERD.png)

## Data Cleaning and Analysis
Pandas will be used to clean the data and perform an exploratory analysis. 

## Machine Learning Model
Before the data was fed into the machine learning model, it was preprocessed. The first- and most-time consuming step was to merge the datasets. The most common column to merge on was the column containing the country name. This is where most of the cleaning was done as names such as St. Lucia versus Saint Lucia wouldn't be found as a match. The majority of this type of cleaning was done manually in Excel since writing lines of code for each country name that didn't match would've been even more time consuming.

Once the cleaning was done, it was time to add the code for the machine learning model. The machine learning model we chose was random forest. This decision came from the fact that our data is labeled (points to supervised machine learning) and that our output (medal count) is numerical. Random forests are made up of many decision trees (a decision tree can be thought of as a collection of if else statements). Each tree in the random forest makes its own prediction on the output. After this, the average of all the outputs is computed to give you the final result. That's to put it in simple terms!

According to the regressor.score function, our model has about 80% accuracy. The RMSE (root mean square error) is about 5. This means that the standard deviation of the residuals (prediction errors) is about 5 medals. Residuals measure how far from the regression line the actual data points are. That's pretty good for about a weeks’ worth of work.

See [cleaning_machine_learningV6.ipynb](https://github.com/cmmgw/Olympic_Analysis/blob/main/Notebooks/cleaning_machine_learningV6.ipynb) Jupyter Notebook.

## Dashboard
An interactive dashboard has been drafted in Tableau to display the findings of the data. A storyboard of the dashboard can be viewed in [Google Slides](https://docs.google.com/presentation/d/1Wga9z9AMnTUY_rI6Oxavn9FzNVRZTxJat0wkYqEAgJU/edit?usp=sharing). See below for additional details.

![Dashboard_Storyboard_Contents.JPG](https://github.com/cmmgw/Olympic_Analysis/blob/main/Graphics/Dashboard_Storyboard_Contents.JPG)

![Dashboard_Storyboard.JPG](https://github.com/cmmgw/Olympic_Analysis/blob/main/Graphics/Dashboard_Storyboard.JPG)

## Presentation
A presentation has been drafted, outlining the project. The presentation can be viewed in [Google Slides](https://docs.google.com/presentation/d/12ERjpT49VNtpophrSCF3aUpZFdYn5OZxcCKLm1VYmOA/edit?usp=sharing).
