# Results of NFL games in CSV format

The results of each NFL game since 1978.  I am looking to back-date this to 1966 - the year of [SuperBowl 1](http://en.wikipedia.org/wiki/Super_Bowl_I).

The 2010 results file will be updated weekly after the Monday night result is in.


## Format

Each file is in [Comma-Separated Value](http://en.wikipedia.org/wiki/Comma-separated_values) format with the following columns:
* League (e.g. NFL)
* Season
* Week
* Kickoff in [ICO 8601](http://en.wikipedia.org/wiki/ISO_8601) format
* Home Team
* Home Score
* Visitors Score
* Visiting Team


## Kickoff

This column will hold the date and time of the kickoff in [Eastern Time](http://en.wikipedia.org/wiki/Eastern_Time_Zone) if it is known (e.g. 2010-09-09T20:30:00-05:00) otherwise it will just hold the date of the match with the time omitted or set to midnight.