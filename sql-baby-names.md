## Using SQLite!

IMPORTANT thing to follow: Give me this, from this, and state conditionals

1) In the year 2013, find out how many babies had your name: 27 

2) Find the highest-rank (and the year) that your name has achieved among baby names: Rank 4099 in 2012

3) Between the years 1980 and 2013, find how many babies in total have been listed by the Social Security Administration in this data. 
126036079


4) Find out how many babies (roughly) have had your name from 1980 to 2013: 365

OK, for this one I tried something like this:
SELECT count, COUNT(*)
FROM ssa_baby_names WHERE name = "Farida" 

And it just gave me 28 as a total, which I know is wrong. But why?

OK, glad to say, figured it out!! Here's the key thing: SUM function.

SELECT SUM (count)
FROM ssa_baby_names WHERE name = "Farida" 

So, result is #365

5) Find the year that had the most male babies born: 1981 

This is the formula I used:
SELECT year, 
MAX (count) FROM ssa_baby_names WHERE sex="M"


6) Find the year in which your name had the highest increase in names-per-100k-babies born:

OK, first, I selected for year and per_100k_ change for my name: 1984, 1997, 1999, 2001, 2005, 2010
SELECT year, per_100k_change
FROM ssa_baby_names WHERE name = "Farida" 

Turns out there's a bunch of years where the highest year was 1. Couldn't figure out how to tell it to just show me the years with change 1 (my max). But I could just see those years: 1984, 1997, 1999, 2001, 2005, 2010


7) Find the year in which your name had the highest decrease in names-per-100k-babies born: 1985, 1998, 2003
Same issue as above.

SELECT count, year
FROM ssa_baby_names WHERE name = "Farida" 

8) Make a line chart showing how your name has changed in popularity over the years
SELECT count, year
FROM ssa_baby_names WHERE name = "Farida" 

Then I went to "Action" dropdown and exported as .csv...

![graph](http://i.imgur.com/JmMCzYy.png)



9) Find out who in our class had the most popular baby name in 1980: Jessica (55985)
Looks like the most popular name is Michael, but no Michael in class...

SELECT name, MAX (count)
FROM ssa_baby_names 

I suspected the most popular names in 1980 maybe where Jessica, or Laura, or Allison

SELECT name, MAX (count) 
FROM ssa_baby_names WHERE name IN ("Allison", "Laura", "Jessica")

Looks like Jessica is it (but could be wrong because I didn't put everyone's name in there.

10) Find out who in our class had the most popular baby name in 2013.

This didn't work. But here is as far as I got before class!
SELECT name, year, MAX (count) 
FROM ssa_baby_names WHERE name in ("Allison", "Laura", "Jessica") WHERE year= "2013"

Find out who in our class has the name that the most babies throughout U.S. history have.
