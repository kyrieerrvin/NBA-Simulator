# NBA-Simulator
Inspired from Ken Jee's own NBA Simulator, scrapes NBA team data from Basketball Reference.

This was supposed to be only for personal use but could probably bring some value to gamblers to have analytics as well.

## Usage
```python
while True:
    year_input = input(str("Year: ")) 
    if year_input == "-":
        break
    team_input = input(str("Team: "))
    encode_input = input(str("Encoding: "))
```
Establishes excel file:
```python
f = open(team_input+".csv", encode_input, encoding="utf-8")
    header = "Team,Game,Date,HC,Opponent,WINorLOSE,TeamPoints,OpponentPoints,FieldGoals,FieldGoalsAttempted,FieldGoalsPCT,FG3,FG3A,FG3_PCT,FT,FTA,FT_PCT,OREB,TRB,AST,STL,BLK,TOV,PF,OPP_FG,OPP_FGA,OPP_FG_PCT,OPP_FG3,OPP_FG3A,OPP_FG3_PCT,OPP_FT,OPP_FTA,OPP_FT_PCT,OPP_ORB,OPP_TRB,OPP_AST,OPP_STL,OPP_BLK,OPP_TOV,OPP_PF\n"
    f.write(header)
```
Then ran into a for loop.

Returns an excel file of team dataset following this column format:
![image](https://user-images.githubusercontent.com/95164825/152002877-a1eb97b9-37a2-47c1-a7eb-fc36a6256972.png)

Sample complete dataset and individual team data is included.

## Contributing
Pull requests regarding optimization of code and/or better update automation of dataset is welcome.

Please make sure to update tests as appropriate.
