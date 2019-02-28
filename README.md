# Cricket Challenge

### You will find the code in cricket_challenge.ipynb


### Data Source and DataLoad
    1. Read the data from https://cricsheet.org/ for which downloaded as odis which is also commited in git repo
    2. Since there are multiple yaml files inside the odis directory hence looping through all files and a list of dataframe called dfs has been created and then finally merged as frame dataframe
    
### Data Cleanup Activity
    1. 'info.teams' column which represents the country name has been converted to Capital Letters to make the column homogeneous
    2. Then data is filtered for columns INDIA and AUSTRALIA only
    3. 'info.city' is the column which tells where the matches has happened, So it has been also converted to UPPER CASE using vectorized function
    4. Then filtered only those records from DataFrame which contains cities 'HYDERABAD', 'NAGPUR', 'RANCHI', 'MOHALI', 'DELHI', because these are the places where matches are going to happen
    5. Then further removed all unecessary columns
    
### DataFrame Records
    Shown the records of 'frame' DataFrame
    
### Problem Statement\[1.\] Winner of the series: India will be winner of Series
    From above DataFrame we can first conclude following
    1. Hyderabad there are two matches in both Australia wins => Chances of Australia to win in Hyderabad
    2. Nagpur there are three macthes and two won by India and 1 won by Australia => Chances of India to win in Nagpur
    3. Delhi one match and India won => Chances of India to win in Delhi
    4. Ranchi there was no result i.e. it was draw => So 50-50 chances of both India and Australia in Ranchi
    5. Mohali no data => So 50-50 chances of both India and Australia in Mohali
    
### Problem Statement\[2.\] Series output : India will win 4 matches and Australia will win 1 match
    In the Problem Statement 1, Chances of India to win in Delhi, Nagpur, Ranchi and Mohali are more and Australia will win in Hyderabad
    
### For getting highest run scorer, wicket taker and sixes we have created a function called getBatsmanAndBowler
    The function getBatsmanAndBowler takes the dataframe 'frame' which is main dataframe and it has a column called 'innings'.
    The 'innings' column is a JSON String which contains 1st Innings and 2 Innings data ball by ball. From there we have created two Dictionaries called innings1_batsman and innings1_bowler. 
    innings1_bowler Column contains batsman wise total runs and total sixes while innings1_bowler contains bowler wise total wicket taken against Australia.
    Then created two DataFrame called 'batsman_df' and 'bowler_df' from 'innings1_batsman' and 'innings1_bowler' respectively.

### Problem Statement\[3.\] Highest Run Scorer: MS Dhoni    
    Sorted the 'batsman_df' by runs column in descending order. The highest scorer is Sachin Tendulkar but he is retired now, So MS Dhoni should be the highest run getter
  
### Problem Statement\[4.\] Maximum Sixes: GJ Maxwell 
    Sorted the 'batsman_df' by sixes column in descending order. GJ Maxwell is the one with higest sixes who is currently playing cricket and not retired
   
### Problem Statement\[5.\] Highest Wicket Taker: RA Jadeja
    Highest wicket taker will be RA Jadeja as I sorted the 'bowler_df' by column wickets in descending order
