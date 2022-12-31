Caribbean Premier League (CPL) Data Analysis and Visualization

Data Source:
The ball  by ball Caribbean Premier League (CPL) data was pulled as a csv file from CricSheets https://cricsheet.org/downloads/. [New Format was used]
Note: In future: to improve I intend to implemenet a Web Scraper with Selenium Webdriver and collect my own data from Espn Cricinfo.

The first row of the ball-by-ball CSV file contains the headers for the file, with each subsequent row providing details on a single delivery.
The headers in the file are:
  * match_id
  * season
  * start_date
  * venue
  * innings
  * ball
  * batting_team
  * bowling_team
  * striker
  * non_striker
  * bowler
  * runs_off_bat
  * extras
  * wides
  * noballs
  * byes
  * legbyes
  * penalty
  * wicket_type
  * player_dismissed
  * other_wicket_type
  * other_player_dismissed

For clarification: 
"innings" contains the number of the innings within the match. If a match is
one that would normally have 2 innings, such as a T20 or ODI, then any innings
of more than 2 can be regarded as a super over.

"ball" is a combination of the over and delivery. For example, "0.3" represents
the 3rd ball of the 1st over.

"wides", "noballs", "byes", "legbyes", and "penalty" contain the total of each
particular type of extras, or are blank if not relevant to the delivery.

If a wicket occurred on a delivery then "wicket_type" will contain the method
of dismissal, while "player_dismissed" will indicate who was dismissed. There
is also the, admittedly remote, possibility that a second dismissal can be
recorded on the delivery (such as when a player retires on the same delivery
as another dismissal occurs). In this case "other_wicket_type" will record
the reason, while "other_player_dismissed" will show who was dismissed.



Data Cleaning:
Using Pandas and NumPy, the Data was cleaned: 
taking care of Null Values in the Data Set and also altering some Non-Null Values to my preference, for easier analysis, 
for example: wides, no balls, byes, legbyes, penalty : if Null => 0 else 1 , wicket_type: if Null => No wicket , player_dismissed: if Null => No dismissal.

I also changed some of the Franchise names to take care of rebranding and even added 3 extra columns to make it simpler to pull specific values; for visualization.
It was then formatted and sorted to my preference.

(Note each step is explained via comments in the Jupyter Notebook)



Data Visualization:
Using Pandas, NumPy, Matplotlib and Seaborn; I explored, analysed and visualized the cleaned data; extracting several useful statistics and creating pivot Tables, plotting barcharts, piecharts, Stripplots etc. 

The entire list of Stats Derived is given below: 

OVERALL:
1) List of Seasons
2) List of Venues
3) List of ALL Teams (Not Franchises)
4) List of All Franchises
5) First ball of CPL history
6) Number of CPL matches played, in each season
7) Number of CPL matches played, at each Venue
8) Number of CPL matches played, by each Franchise

BATTING STATS:
1)Total Runs Scored by each Franchise
2)Top 10 Leading Run Scorers in the CPL
3)Average Powerplay runs by each Franchise
4)All CPL century- makers and number of centuries each
5) 10 Bastman with most CPL Half Centuries
6) List of the Batsman with the greatest number of runs in each season
7) List of the Top 10 greatest number runs scored by a single player in a season
8)10 Bastman with the most Fours struck
9)Top 10 Highest Team Totals in CPL History
10)10 Bastman with the most Sixes struck
11)Number of CPL Sixes Hit by Season
12)Top 10 Highest individual Scores and Batsman
13)Top 10 individual innings with the Highest Number of 6s

BOWLING STATS:
1)Leading wicket Takers by Season
2)Bowlers with the most wickets each season (and number of wickets)
3)Top 10 Leading Wicket-Takers in the CPL
4)Number of Wickets Taken by each CPL Franchise
5)Bowlers with most dot balls
6)Bowlers with most CPL Maiden Overs
7)Number of Extras Conceded by All Franchises in CPL History
8)Number of Wides bowled by each franchise in CPL History
9)Number of No Balls bowled by each franchise in CPL History
10)Top 10 Bowlers with Most No-Balls in CPL History
11)Top 10 Bowlers with most runs conceded in an innings


