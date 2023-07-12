# Covid-19-Data-Analysis-Sqoop-and-Hive

## Problem Overview: 
Aim is to use the Big data tools and technologies for the analysis of the two given datasets based on covid-19 spread in India and the Testing associated with it and try to get some insights.The data is available between 1st -April to 10th June duration. 

## Detailed Problem Statement:  
A ] Need to create a data flow pipeline ,where data initially resides in RDBMS and needs to be brought to Hive so as to get a consolidated view of covid cases details as well as testing details,taken together in one table.  
B ] Optimizations during sqoop import/export , hive optimizations have to be considered.Also password encryption in sqoop to be used.  
C ] The data field is not in proper format and has to be taken care  
D ] Try to infer from the final consolidated table in Hive like whether there is any discrepency between Number of confirmed covid cases in the state Vs.Number of Positive Samples collected during testing. Which state shows least discrepency.  
E ] Run some more interesting queries from your end in hive to get more insights on the consolidated data .  

Sample Query -For every state, find the total number of confirmed cases reported and also total number of positive samples tested,in the entire
duration of 2months, starting with the state with the highest cases.  
Dataset- Two csv files are provided -  
1. StatewiseTestingDetails.csv  
2. Covid19_india.csv
   
StatewiseTestingDetails.csv :This dataset contains statewise,daily count of Testing performed in India.  
Columns : Seq,Date,State,TotalSamples,Negative,Positive  

Covid19_india.csv:This dataset contains statewise,daily count of covid cases in India.  
Columns : Sno,Date,State/UnionTerritory,Cured,Deaths,Confirmed  


### Points to Note/Few Assumptions  
1. We do not have data for every state in these two files.Also we do not have data for every date in these two files.Some States and dates might be missing in these datasets.  
2. Joining of two datasets might not be of much signifiance in this case but this is to check the understanding of hive and whether in real time you can work on this type of dataflow involving hive and sqoop.  
3. We assume that more data is added to both the tables on a frequent basis.So we need an incremental sqoop job  
4. More queries on state and dates can come in future so , bucketing and partitioning to be used on these columns.  
5.We assume that StatewiseTestingDetails.csv is the smaller dataset among the two.
