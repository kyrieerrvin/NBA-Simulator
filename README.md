# NBA-Simulator
Inspired from Ken Jee's own NBA Simulator, scrapes NBA team data from Basketball Reference

## Usage
```python
year_input = input(str("Year: ")) # gets year
    if year_input == "-":
        break
    team_input = input(str("Team: ")) # gets team
    encode_input = input(str("Encoding: ")) # gets excel encoding (w or a)

Returns an excel file of team dataset following this column format:
![image](https://user-images.githubusercontent.com/95164825/152002877-a1eb97b9-37a2-47c1-a7eb-fc36a6256972.png)

## Contributing
Pull requests regarding optimization of code and/or better update automation of dataset is welcome.

Please make sure to update tests as appropriate.
