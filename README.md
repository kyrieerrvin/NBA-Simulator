# NBA-Simulator
Inspired from Ken Jee's own NBA Simulator, scrapes NBA team data from Basketball Reference

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
```python
    for stats in d_table.find_all('tbody'):
        rows = stats.find_all('tr')
        for row in rows:
            try:
                game = row.find('td', attrs={'data-stat': 'game_season'}).text
                date = row.find('td', attrs={'data-stat' : 'date_game'}).text
                home = row.find('td', attrs={'data-stat': 'game_location'}).text
                if home == "":
                    home = "Home"
                else:
                    home = "Away"
                opp = row.find('td', attrs={'data-stat': 'opp_id'}).text
                result = row.find('td', attrs={'data-stat': 'game_result'}).text
                pts = row.find('td', attrs={'data-stat': 'pts'}).text
                opp_pts = row.find('td', attrs={'data-stat': 'opp_pts'}).text
                fg = row.find('td', attrs={'data-stat': 'fg'}).text
                fga = row.find('td', attrs={'data-stat': 'fga'}).text
                fg_pct = row.find('td', attrs={'data-stat': 'fg_pct'}).text
                fg3 = row.find('td', attrs={'data-stat': 'fg3'}).text
                fg3a = row.find('td', attrs={'data-stat': 'fg3a'}).text
                fg3_pct = row.find('td', attrs={'data-stat': 'fg3_pct'}).text
                ft = row.find('td', attrs={'data-stat': 'ft'}).text
                fta = row.find('td', attrs={'data-stat': 'fta'}).text
                ft_pct = row.find('td', attrs={'data-stat': 'ft_pct'}).text
                orb = row.find('td', attrs={'data-stat': 'orb'}).text
                trb = row.find('td', attrs={'data-stat': 'trb'}).text
                ast = row.find('td', attrs={'data-stat': 'ast'}).text
                stl = row.find('td', attrs={'data-stat': 'stl'}).text
                blk = row.find('td', attrs={'data-stat': 'blk'}).text
                tov = row.find('td', attrs={'data-stat': 'tov'}).text
                pf = row.find('td', attrs={'data-stat': 'pf'}).text

                opp_fg = row.find('td', attrs={'data-stat': 'opp_fg'}).text
                opp_fga = row.find('td', attrs={'data-stat': 'opp_fga'}).text
                opp_fg_pct = row.find('td', attrs={'data-stat': 'opp_fg_pct'}).text
                opp_fg3 = row.find('td', attrs={'data-stat': 'opp_fg3'}).text
                opp_fg3a = row.find('td', attrs={'data-stat': 'opp_fg3a'}).text
                opp_fg3_pct = row.find('td', attrs={'data-stat': 'opp_fg3_pct'}).text
                opp_ft = row.find('td', attrs={'data-stat': 'opp_ft'}).text
                opp_fta = row.find('td', attrs={'data-stat': 'opp_fta'}).text
                opp_ft_pct = row.find('td', attrs={'data-stat': 'opp_ft_pct'}).text
                opp_orb = row.find('td', attrs={'data-stat': 'opp_orb'}).text
                opp_trb = row.find('td', attrs={'data-stat': 'opp_trb'}).text
                opp_ast = row.find('td', attrs={'data-stat': 'opp_ast'}).text
                opp_stl = row.find('td', attrs={'data-stat': 'opp_stl'}).text
                opp_blk = row.find('td', attrs={'data-stat': 'opp_blk'}).text
                opp_tov = row.find('td', attrs={'data-stat': 'opp_tov'}).text
                opp_pf = row.find('td', attrs={'data-stat': 'opp_pf'}).text

                f.write(team_input + "," + game + "," + date + "," + home + "," + opp + "," + result + "," + pts + "," + opp_pts + "," + fg + "," + fga + "," + fg_pct + "," + fg3 + "," + fg3a + "," + fg3_pct + "," + ft + "," + fta + "," + ft_pct + "," + orb + "," + trb + "," + ast + "," + stl + "," + blk + "," + tov + "," + pf + "," + opp_fg + "," + opp_fga + "," + opp_fg_pct + "," + opp_fg3 + "," + opp_fg3a + "," + opp_fg3_pct + "," + opp_ft + "," + opp_fta + "," + opp_ft_pct + "," + opp_orb + "," + opp_trb + "," + opp_ast + "," + opp_stl + "," + opp_blk + "," + opp_tov + "," + opp_pf + "\n")
                print(game, date, result)
                print("-" * 50)
            except:
                continue
```
Returns an excel file of team dataset following this column format:
![image](https://user-images.githubusercontent.com/95164825/152002877-a1eb97b9-37a2-47c1-a7eb-fc36a6256972.png)

## Contributing
Pull requests regarding optimization of code and/or better update automation of dataset is welcome.

Please make sure to update tests as appropriate.
