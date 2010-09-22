# Results of NFL games in CSV format

The results of each NFL game since 1978.  I am looking to back-date this to 1966 - the year of [SuperBowl 1](http://en.wikipedia.org/wiki/Super_Bowl_I).

The 2010 results file will be updated weekly after the Monday night result is in.


## Format

Each file is in [Comma-Separated Value](http://en.wikipedia.org/wiki/Comma-separated_values) format with the following columns:

| Column         | Format                                                   | Example
| -------------- | -------------------------------------------------------- | -----------
| season         | Number (4 digits)                                        | 2010
| week           | The week number since opening day (1-22)                 | 1
| kickoff        | [ISO 8601](http://en.wikipedia.org/wiki/ISO_8601) format | 2010-09-09T20:30:00-05:00
| home_team      | Team name, without city                                  | Saints
| home_score     | Number                                                   | 14
| visitors_score | Number                                                   | 9
| visiting_team  | Team name, without city                                  | Vikings


### Kickoff

This column will hold the date and time of the kickoff in [Eastern Time](http://en.wikipedia.org/wiki/Eastern_Time_Zone) if it is known (e.g. 2010-09-09T20:30:00-05:00) otherwise it will just hold the date of the match with the time set to midnight.

## Disclaimer

I am merging multiple datasets and working through the combined data set to ensure it is accurate. I have already found and corrected some errors, but I am sure that others remain.  Once I have cross referenced with other sources I shall remove this warning.


These teams are missing some home games:

    1978|Cowboys|7
    1979|Broncos|7
    1980|Dolphins|7
    1980|Oilers|7
    1980|Redskins|7
    1981|Oilers|7
    1983|Chargers|7
    1984|Jets|7
    1984|Vikings|7
    1985|Broncos|7
    1985|Chargers|7
    1985|Cowboys|7
    1986|Chargers|7
    1988|Cowboys|7
    1989|Cowboys|7
    1989|Seahawks|7
    1990|Cardinals|7
    1991|Vikings|7
    1992|Cardinals|7
    1994|Bears|7
    1994|Colts|7
    1995|Cardinals|7
    1995|Colts|7
    1995|Vikings|7
    1996|Bears|7
    1996|Colts|7
    1996|Giants|7
    1997|Lions|7
    1997|Panthers|7
    1998|Bills|7
    1998|Cowboys|7
    1999|Chiefs|7
    2001|49ers|7
    2001|Buccaneers|7
    2001|Chiefs|7
    2001|Cowboys|7
    2005|Saints|7
    2008|Saints|7
    
    sqlite>     select season, home_team, count(*) as home_games 
       ...>     from Game 
       ...>     where season not in (1982,1987) and season>=1978
       ...>     group by season, home_team 
       ...>     having home_games < 8;
    