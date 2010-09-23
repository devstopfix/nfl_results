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

I am merging multiple datasets and working through the combined data set to ensure it is accurate. I have already found and corrected some errors, but I am sure that others remain.  Once I have cross referenced the data with other sources I shall remove this warning.

These teams are missing some home games:

		2002|Giants|7
		2003|Redskins|7
		2005|Saints|7
		2006|Steelers|7
		2008|Saints|7
		2009|Steelers|7

		select season, home_team, count(*) 
		from Game 
		where season>1987 
		group by season, home_team 
		having count(*) <= 7;
    
These teams are missing some away games:

		2003|Jets|7
		2005|Giants|7
		2005|Raiders|7
		2006|Dolphins|7
		2007|Saints|7
		2008|Redskins|7
		2009|Titans|7
		
		select season, visiting_team, count(*) 
		from Game 
		where season>1987 
		group by season, visiting_team 
		having count(*) <= 7;
		