# Final project - Website
_By Eskil Rasmussen s203817 - Group 22
Course: 02806: Social Data Analysis and Visualization

## Introduction
Welcome to an exploration of how the COVID-19 pandemic reshaped mobility patterns in Denmark. 

This project combines hospitalization data and road traffic counts to tell a data-driven story of how restrictions, case severity, and human behavior intertwined over the course of the crisis.

My goals are to:
* Illustrate regional differences in pandemic severity (hospitalizations).
* Reveal how traffic volumes rose and fell in response to both official policies and the unfolding health crisis.

## Data Sources

Corona data: Danish historical COVID-19 figures from SST (Staten Serum Institut): https://www.ssi.dk//sygdomme-beredskab-og-forskning/sygdomsovervaagning/c/historiske-covid-19-opgoerelser 

Traffic Flow: Danish traffic data is hard to acces by day. Only avaliable data from DK was specific local data counts, and on average over a year. which is insufficent if we want to show trends after e.g. closing of borders. Traffic flow pr day used is hence from the German data bank www.bast.de and data is from right across the border on the german A7 autobahn at Ellund is used: https://www.bast.de/DE/Verkehrstechnik/Fachthemen/v2-verkehrszaehlung/Daten/2022_1/Jawe2022.html?nn=1817946&cms_detail=1109&cms_map=0

Timeline & Policies: Key dates of national lockdowns, reopening phases, and policy announcements are from here: https://www.ssi.dk/-/media/arkiv/subsites/covid19/presse/tidslinje-over-covid-19/covid-19-tidslinje-for-2020-2022-lang-version---version-1---april-2022.pdf2024


## 1. Denmarks Pandemic Trends
Denmark confirmed its first COVID-19 case on February 27, 2020, and quickly moved to close borders (March 13) and impose a nationwide lockdown on March 16—earlier than many European neighbors, including France and Germany

Below is a combined view of:
* Weekly confirmed cases (stacked area by region)
* Weekly hospital admissions (red line)
* Key policy and variant events (vertical annotations)


<img src="/assets/Area plot.png">


Figure 1. COVID‑19 cases (stacked by region) and hospitalizations per week (7‑day rolling averages), annotated with major lockdowns and reopening phases.

Key takeaways:
* The first national lockdown (March 2020) coincides with an early hospitalization peak, but case counts remained relatively low.
* Winter 2020–21 saw a larger second wave of cases and hospitalizations.
* The Omicron surge (late 2021 / early 2022) produced the highest hospitalization and infection rates across all regions.
* Following Omicron, hospitalizations dropped rapidly even as case counts plateaued, reflecting vaccination and changing severity.
* An Interesting opservation can be made bestween the peaks of the two graphs: They are shifted - This is most likely due the time it takes to become ill after you get infected. but how big is this shift?

### 1.1 Correlation and lag analisys
Just for fun it would be intersting to see how well the two correlate, and what the acutal lag is.
Below is a scatter plot made to show correlation between hopitalizations and cases here with a guessed shift of 14 days - As that was the amount of time one had to isolate themself if you got corona.

<img src="/assets/Corr covid and hosp 14 day lag.png">

Figure 2. Correlation between cases and hospitalizations with a lag of 14 days. - The pearson correlation is 0.89

But how many days is the hopitalizations actually lagging behind? figure 3 shows the pearson correlation between the two compared to days of lag

<img src="/assets/Corr between cases and hosp vs lag days.png">

Figure 3. Correlation versus lag days, peaking at ~0.89 around 14 days – indicating hospitalizations typically follow case surges by about 2-3 weeks.

This shows that the guess at 14 days was coorrect, but at around 21 days, we also see a peak. - Could be due to men and women maybe having different avererage times before they get really sick. - We could dive into that rabbit hole, but lets proceed for now :).

## 2. Traffic flow analisys
Next, we analyze vehicle counts at the Ellund border station. 

Here is a graph showing average weekly traffic over time.

<img src="/assets/weekly traffic avg.png">

Figure 4. Average amount of weekly traffic for the years 2019-2022.

Its seen that it varies a lot thoughout the years, with peaks in the summer holiday (July-August) and lows during winter and early spring. But no clear trends related to corona are showing.

To get an idea of different types of traffic we can try to group all passenger cars and motorcycles as "private" traffic and all trucks and vans as "work" traffic:

<img src="/assets/weekly traffic avg by vehicle.png">

Figure 5. Amount of private vs work traffic. 

Its clear to see that the season especially impact private traffic, and doens't impact work traffic as much.

There is some wierd drops in the beginning of 2020 and 2021 tho for work related traffic, lets compare this with some corona data. 


## 3. Covid vs traffic flow

By comparing 2019–22 traffic to a 2015–17 baseline, we can highlight how lockdowns and rising case counts influenced cross-border movement. 
This is below plottet along with hospitalisations both as a graph and as mapped out on a map of the regions in denmark. Oppasity showing amount of hospitalisations in each region.

<iframe src="/assets/ellund_covid_map_hosp_traffic.html" width="1050" height="1150"></iframe>

Figure 6. Map of amount of hospitalizations across region along with total number of hopitalizations, the traffic anomaly based on an average made of data from the same checkpoint in the years 2015-2017 (before corona), and big event/nationwide political decisions made due to corona. The plot has a Slider i the bottom and the event are toggable 

* It is clear to see that peaks in private traffic reductions align closely with hospitalization surges, especially during first and second lockdowns.

* Work traffic remained above 50% of baseline even when hospital strain was highest, underscoring essential mobility.

* The two-week hospitalization lag behind cases also manifests in traffic: private flow dips slightly after peaks in case growth.

* The region around copenhagen is hit the hardest compared to the others - Especially in the early waves.


## Limits and learnings

* German nation wide events during corona propably have an impact on the data as well as the traffic data is from the german border.

* Good traffic data on volume of cars pr day prooved very hard to find for danish roads, and it took a lot of time sourcing the german data. Nice to know for another time that the germans like their data. :)

**To see how the plots are made you can click [here](Boiii7.ipynb) for a notebook experince.**

