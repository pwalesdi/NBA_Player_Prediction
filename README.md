# NBA Player Prediction

This project is an attempt to glean information about NBA Players. When teams invest in a player they are taking a risk. They pay them millions of dollars for the promise of a return on the basketball court and or through marketing/ticket sales. These two are obviously related but that relationship is not one to one. Here I wanted to focus on whether you could predict the future performance of an NBA player based on his statistics in his first two years. I had a number of different theories about what might be interesting and useful. Ultimately I decided that I wanted to see the following **`Can I use a players stats from their first two seasons in the NBA, to predict if they will achieve a benchmark`**. What benchmark? Here I have decided that I am going to try to predict if a player will have a [PER](https://www.basketball-reference.com/about/per.html) of over 20 and play over 1000 minutes. Below I will walk through the steps that I used to preprocess the dataframes and prepare for modeling. 

I have prepared two dataframes. The first is called `second_year_prime` the second dataframe is called `first_second_seasons_agg`. In this notebook I am going to focus on `second_year_prime`. `second_year_prime` is a collection of second year seasons from NBA players dating back to the 2006 season. It only includes players who have played 5 years after their second season (7 year NBA veterans or more). The dataframe has a column called target that contains a `1` if the player will go on to reach the benchmark of higher than 20 PER and over 1200 minutes played and a `0` if the player does not go on to reach that benchmark. I split the dataframe up into training and testing and trained multiple classification models to see how the model can predict if a player reaches the benchmark.

 ### Data dictionary
 | Column        | Type | Description                                              |
|---------------|-----------|----------------------------------------------------------|
| Player_name | object | First and Last Name of the Player    |
| player_id | object   | unique identifier of player                  |
| SEASON | int | The NBA season that the row corresponds with. The 2018-19 season is coded as 2019 |
| Tm_x | object | The NBA the player is on |
| DRAFT_YEAR+1 | float | The players rookie year season |
| Draft_team | object | The team that drafted the player |
| Pk | float | the pick they were selected in the NBA Draft |
| Age | int | Their age during that season |
| Pos | object | the position they are coded as by basketball-reference |
| G | int | number of games they played in the season |
| MP | int | numner of minutes they played in a system |
| PER | float   | Player Effieciency Rating |
| TS% | float   | True Shooting Percentage |
| 3PAr | float   | Percentage of FG Attempts from 3-Point Range |
| FTr | float  | Number of FT Attempts Per FG Attempt |
| ORB% | float   | An estimate of the percentage of available offensive rebounds a player grabbed while he was on the floor |
| DRB% | float   | An estimate of the percentage of available defensive rebounds a player grabbed while he was on the floor |
| TRB% | float   | An estimate of the percentage of available rebounds a player grabbed while he was on the floor |
| AST% | float   | An estimate of the percentage of teammate field goals a player assisted while he was on the floor |
| STL% | float   | An estimate of the percentage of opponent possessions that end with a steal by the player while he was on the floor |
| BLK% | float   | An estimate of the percentage of opponent two-point field goal attempts blocked by the player while he was on the floor |
| TOV% | float   | An estimate of turnovers committed per 100 plays |
| USG% | float   | An estimate of the percentage of team plays used by a player while he was on the floor |
| OWS | float   | An estimate of the number of wins contributed by a player due to his offense |
| DWS | float   | An estimate of the number of wins contributed by a player due to his defense |
| WS | float   | An estimate of the number of wins contributed by a player |
| WS/48	| float   | An estimate of the number of wins contributed by a player per 48 minutes (league average is approximately .100) |
| OBPM | float   | A box score estimate of the offensive points per 100 possessions a player contributed above a league-average player, translated to an average team |
| DBPM | float   | A box score estimate of the defensive points per 100 possessions a player contributed above a league-average player, translated to an average team |
| BPM | float   | A box score estimate of the points per 100 possessions a player contributed above a league-average player, translated to an average team |
| VORP | float   | A box score estimate of the points per 100 TEAM possessions that a player contributed above a replacement-level (-2.0) player, translated to an average team and prorated to an 82-game season |
| College | object   | The college the player attended |
| Yrs | float   | the numeber of years the player has played in the NBA |
| PTS | float   | total points the player scored that season |
| TRB | float   | total rebounds the player recorded that season |
| AST | float   | total assists the player recoeded that season |
| FG%	| float   | field goal percentage for the season |
| 3P%	| float   | 3 point field goal percentage for the season |
| FT%	| float   | free throw percentage for the season |
| PPG | float   | points per game for the season |
| RPG | float   | rebounds per game for the season |
| APG | float   | assists per game for the season |
| draft_round | float   | the round the player was drafted in |

## Additional Writing
[When To Give Up: An examination into the value of NBA players relative to their draft status, their likelihood to succeed, and how to determine the value of an asset.
](https://towardsdatascience.com/when-to-give-up-117e2e2acdc9)



## Visuals
![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/ws_per48_dftYR_byRound.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/ws_per48_dftYR_byRound_1.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/ws_per48_dftYR_byRound_2.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/2nd_year_best.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/3rd_year_best.png)

![alt text](https://github.com/pwalesdi/NBA_Player_Prediction/blob/master/Images/4th_year_best.png)

