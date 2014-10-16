## Using SQLite!

1) In the year 2013, find out how many babies had your name: 27 

2) Find the highest-rank (and the year) that your name has achieved among baby names: Rank 4099 in 2012

3) Between the years 1980 and 2013, find how many babies in total have been listed by the Social Security Administration in this data. 
126036079


4) Find out how many babies (roughly) have had your name from 1980 to 2013

OK, for this one I tried something like this:
SELECT count, COUNT(*)
FROM ssa_baby_names WHERE name = "Farida" 

And it just gave me 28 as a total, which I know is wrong. But why?

OK, glad to say, figured it out!! Here's the key thing: SUM function.

SELECT SUM (count)
FROM ssa_baby_names WHERE name = "Farida" 

So, result is 365

Find the year that had the most male babies born
Find the year in which your name had the highest increase in names-per-100k-babies born
Find the year in which your name had the highest decrease in names-per-100k-babies born
Make a line chart showing how your name has changed in popularity over the years
Find out who in our class had the most popular baby name in 1980.
Find out who in our class had the most popular baby name in 2013.
Find out who in our class has the name that the most babies throughout U.S. history have.
