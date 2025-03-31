# Short data story of large baseball events in San Francisco
_By Eskil Rasmussen s203817 and Jakob Tonkunas Christensen s203769_
## Introduction
This exploration is based on data provided by the City of San Francisco through DataSF on ['Public Safety'](https://datasf.org/opendata/). Two datasets of crime incidents have been combined and filtered to contain categorized incidents from the full years 2003-24 with date and location. For this data story, we will only use data from 2007-14.

## Baseball games
Downtown San Francisco is home to Oracle Park, where the San Francisco Giants of the MLB play their home games. It's beautifully located on the north-eastern shore, with views of the SF bay over South Beach Harbor from the stands. The ballpark has hosted several of the biggest MLB games, as the [2007 MLB All-Star game](https://en.wikipedia.org/wiki/2007_Major_League_Baseball_All-Star_Game) and [2010](https://en.wikipedia.org/wiki/2010_World_Series), [2012](https://en.wikipedia.org/wiki/2012_World_Series), and [2014](https://en.wikipedia.org/wiki/2014_World_Series) World Series (MLB Finals) were played here.

As large sports events often serve alcohol and have a reputation for having drunk fans, who can be disruptive, we wanted to explore whether the crime data backs this up.

## Bar charts
We will look at the crime categories 'larceny/theft', 'assault', 'vandalism', 'drug/narcotic' and 'liquor laws', as these are assumed to be most related to intoxication. The plots display the hourly crime from midnight the day of the games until 7 AM the following day.

![average](average.png)

Unfortunately, there is no clear trend for the occurrence of crime. This is likely influenced by the data covering such a large area that any related changes gets washed out.

## Map

Instead, we will look at a map. This is hexplot of crimes on game days compared to the average of a subsample of days in 2007-14.

![hexmap](hexmap.png)

Here, we see a stronger colored hexagon right next to Oracle Park!

## Bokeh
Finally, we have an interactive map of the crimes on game days, where days and categories can be toggled on and off to explore.

<iframe src="/assets/interactive_crime.html" width="800" height="600"></iframe>
