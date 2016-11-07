# Predicting NBA Games using SQL Server R Services

In this repo I included the R code, T-SQL code, and the database used in my presentation on SQL Server R Services. The steps that I used in the presentation are as follows:

   1. I developed the models to predict the final quarter of the 2008 - 2009 NBA season using data from the first 3/4 of the season. The model was developed in RTVS. Listed are the R scripts used to develop the model broken out into logical units of work:
    - STEP_1.R
    - STEP_2.R
    - STEP_3.R
    - STEP_4.R
    - STEP_5.R
    - STEP_6.R
    - STEP_7.R

   2. I created the NBAModels table and the AddModel stored procedure in the NBAPredictions database. The NBAModels table warehouses the actual model as well as additional columns for the model attributes. The AddModel stored procedure is used to get the serialized version of the model from R, convert the model to a binary format, then insert the model along with some of its attributes into the NBAModels table.

   3. I executed the STEP_8.R script to add the 8 models and some of its attributes to the NBAModels table.

   4. I created the AwayRecords.sql, HomeRecords.sql, OverallRecords.sql, and ScoreData.sql views. These views were used to create the features for the games in the last quarter of the season.

   5. Executed the PredictGameBatchMode stored procedure to predicted the last quarter of the season.
   
   6. I visualized the results in Power BI via the NBA_Report.pbix file.

The raw data was obtained from the www.basketballgeek.com/data/ website. I used the CombineGamePlayByPlayData.R script to combine all of the 1,176 individual game data files into one data frame and saved that data frame to a csv file.
