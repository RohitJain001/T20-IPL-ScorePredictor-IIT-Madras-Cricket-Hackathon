# T20-IPL-ScorePredictor

Predicting scores of IPL Matches after 6 overs,
Dataset can be downloaded from cricsheet.org website (IPL dataset 2008 - 2020)

#### Features were:
match_id, season, start_date, venue, innings, ball, batting_team, bowling_team, striker, non_striker, bowler, runs_off_bat, extras, wides, noballs, byes, legbyes, penalty, wicket_type, player_dismissed, other_wicket_type, other_player_dismissed

## Data Preprocessing
1) Dropped the irrelavant features such as 'other_player_dismissed','other_wicket_type', 'penalty','player_dismissed','start_date'
2) Agregated the sum of all types of scores to 1 column as `total_runs` and dropped the individual columns of runs.
3) Few Team names were changed in recent years such as `Delhi Daredevils to Delhi Capitals` & `Kings XI Punjab to Punjab Kings`, renamed them 
4) Dropped the data of the teams that were present in past such as `Rising Pune Supergiant`, `Gujrat Lions`, `Deccan Chargers`.
5) Renamed the stadium names to 1 which were same but named differently such as `MA Chidambaram Stadium, Chepauk` to `MA Chidambaram Stadium` & `Sardar Patel Stadium, Motera` to `Narendra Modi Stadium`
6) Filtered the data with 2021 stadiums, teams & 2 innings & With overs <= 6.0
7) Label encoded the Bowler & Batsman. Created dictionary of mappings.
8) Grouped the data with `match_id & innning` & aggregated runs, took batting team & balling team & venue.
9) Created the encoding of 10 Batsmen & Bowlers and created columns for it.

Final Columns were innings, Batting Team, Bowling Team, Venue and batsmen & bowlers.


## Data Training
1) Splitted the data in trainig (80%) & testing (20%)
2) Used Randomized Search CV & trained Random Forest Regressor
3) Also Trained Model with Lasso Regressor

Created the joblib files for model & 4 dictionaries (Batsmen, Bowler, Team & Venue) for future use.

## Predictions
Was expected to share the predictions and model file with the IIT Madras team for each day's match score prediction in 1st powerplay before 7:00 pm in the evening & watch match from 7:30 pm


<br><br><br>
Unfortunately, In 2021 due to Covid 19 IPL went on hold from May 2, 2021. Because of this Competition closed. IPL continued in September. 
But it was truly enjoyable sharing predictions for each day for match in April and watch match live to know how good is my model & estimation of score.
