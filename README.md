# NBA Player Prediction

This project is an attempt to glean information about NBA Players. When teams invest in a player they are taking a risk. They pay them millions of dollars for the promise of a return on the basketball court and or through marketing/ticket sales. These two are obviously related but that relationship is not one to one. Here I wanted to focus on whether you could predict the future performance of an NBA player based on his statistics in his first two years. I had a number of different theories about what might be interesting and useful. Ultimately I decided that I wanted to see the following **`Can I use a players stats from their first two seasons in the NBA, to predict if they will achieve a benchmark`**. What benchmark? Here I have decided that I am going to try to predict if a player will have a [PER](https://www.basketball-reference.com/about/per.html) of over 20 and play over 1000 minutes. Below I will walk through the steps that I used to preprocess the dataframes and prepare for modeling. 

I have prepared two dataframes. The first is called `second_year_prime` the second dataframe is called `first_second_seasons_agg`. In this notebook I am going to focus on `second_year_prime`. `second_year_prime` is a collection of second year seasons from NBA players dating back to the 2006 season. It only includes players who have played 5 years after their second season (7 year NBA veterans or more). The dataframe has a column called target that contains a `1` if the player will go on to reach the benchmark of higher than 20 PER and over 1200 minutes played and a `0` if the player does not go on to reach that benchmark. I split the dataframe up into training and testing and trained multiple classification models to see how the model can predict if a player reaches the benchmark.

 ### Data dictionary
 | Column        | Type | Description                                              |
|---------------|-----------|----------------------------------------------------------|
| Player_name | object | unique identifier of movie    |
| player_id | object   | unique identifier of user                  |
| SEASON | int | rating was given to a movie by a user (scale 1-5) |
| Tm_x | object | date when rating was given to a movie by a user |
| DRAFT_YEAR+1 | float64 | date when rating was given to a movie by a user |
| Draft_team | object | date when rating was given to a movie by a user |
| Pk | float64 | date when rating was given to a movie by a user |
| Age | int64 | date when rating was given to a movie by a user |
| Pos | object | date when rating was given to a movie by a user |
| G | int64 | date when rating was given to a movie by a user |
| MP | int64 | date when rating was given to a movie by a user |
| PER | float64   | date when rating was given to a movie by a user |
| TS% | float64   | date when rating was given to a movie by a user |
| 3PAr | float64   | date when rating was given to a movie by a user |
| FTr | float64   | date when rating was given to a movie by a user |
| ORB% | float64   | date when rating was given to a movie by a user |
| DRB% | float64   | date when rating was given to a movie by a user |
| TRB% | float64   | date when rating was given to a movie by a user |
| AST% | float64   | date when rating was given to a movie by a user |
| STL% | float64   | date when rating was given to a movie by a user |
| BLK% | float64   | date when rating was given to a movie by a user |
| TOV% | float64   | date when rating was given to a movie by a user |
| USG% | float64   | date when rating was given to a movie by a user |
| OWS | float64   | date when rating was given to a movie by a user |
| DWS | float64   | date when rating was given to a movie by a user |
| WS | float64   | date when rating was given to a movie by a user |
| WS/48	| float64   | date when rating was given to a movie by a user |
| OBPM | float64   | date when rating was given to a movie by a user |
| DBPM | float64   | date when rating was given to a movie by a user |
| BPM | float64   | date when rating was given to a movie by a user |
| VORP | float64   | date when rating was given to a movie by a user |
| College | object   | date when rating was given to a movie by a user |
| Yrs | float64   | date when rating was given to a movie by a user |
| PTS | float64   | date when rating was given to a movie by a user |
| TRB | float64   | date when rating was given to a movie by a user |
| AST | float64   | date when rating was given to a movie by a user |
| FG%	| float64   | date when rating was given to a movie by a user |
| 3P%	| float64   | date when rating was given to a movie by a user |
| FT%	| float64   | date when rating was given to a movie by a user |
| PPG | float64   | date when rating was given to a movie by a user |
| RPG | float64   | date when rating was given to a movie by a user |
| APG | float64   | date when rating was given to a movie by a user |
| draft_round | float64   | date when rating was given to a movie by a user |




## Visuals
![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/ws_per48_dftYR_byRound.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/ws_per48_dftYR_byRound_1.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/ws_per48_dftYR_byRound_2.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/2nd_year_best.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/3rd_year_best.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/4th_year_best.png)

