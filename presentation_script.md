#### s1
Hi everyone, I'm glad to be here to share the result of WomenTechWomenYes Subway Outreach Team Arrangement project

#### s2
The client emailed us and said they would like to place street teams at subway entrances to promote their gala.

There may be multiple control areas in one station, and each team will be placed at a specific control area in the station in a certain time period.

And their event will be at the beginning of the summer 

So I aimed to identify the busiest subway control areas and time periods with the highest sum of entries and exits between March and May in 2021

And my goal is to make a suggestion for the client to know which control areas and what time to place their team during their outreach period 

#### s3
I used public MTA turnstile data which contians almost 3 million rows

The tools I used were SQLite3, Pyhton Pandas, SQLAlchemy, Numpy, and visualization libraries

#### s4
There are 750 control areas in subway systems times 6 periods per day, and times 7 days of the week

So we got more than 30 thousand possiblities

This is the first highlight I would like to share.

I took top 100 busiest control area cross time period and day of the week to see the distritution

Evening from 4 pm to 8 pm  was the busiest time

This showed that the busiest control areas in the morning or in the afternoon may still have more traffic than unbusy control areas in busy evenings

This also matched the result that I found weekdays had higher traffic than weekends

The traffic among weekdays were close although there were slightly more traffic on Fridays and slightly less traffic on Mondays.


#### s5
Another highlight to show top 20 control areas and moments

And it's occuipied by only 3 control areas

R533 at Flushing–Main Street Station was the busiest control area

It also showed the traffic at Flushing–Main Station in the morning was still much higher than many other control areas in the busy evenings

#### s6
Conclusion

we would like to reach out to different people as much as possible

From the pattern, I feel each time period during the weekdays may be the same group of people

So to boraden the outreach, we can find the busiest day of the week for each control area at each time period, and we just go there once on weekday and once on weekend during the outreach period.

I wrote a function to help the client plan the schedule by inputting the number of outreach weeks, the amount of teams, and the weekly outreach capacity per team

Here is an example of the first week schedule with 4-week outreach, 3 teams, and 5 weekly outreaches per team.

The busiest moment overall was R533 Flushing/Main Station on Friday Evening

We definitely will go there on Friday evening once but not on other weekday evenings

The busiest morning for R533 was on Wednesday so we go there on one Wednesday morning not on Friday or other weekdays

We only have 3 teams so we can go to only 3 control areas in one time period on one single day 

The function wll help to limit this by the input

#### s7
Future work

Will need to find the location information of the control areas, maybe the team can ask MTA staff when they are there

Can match some big events like sport games, concert

I'm also thinking of some mapping data

#### s8
Thank you for your time and listening

Some appendix are attahched in the end of these slides for your reference

Thank you
