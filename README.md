# Water Stock Analysis

-------

## What's Water Stock??



Farms across the United States that have or attend to cattle have access to water stock systems (public or private). These [water stock systems](https://www.usgs.gov/mission-areas/water-resources/science/livestock-water-use) can be at various levels: Surplus, Adequate, Short, and Very Short. 

We attempt to highlight trends in water stock levels across the states of Missouri, North Dakota, New Mexico, Utah, and Wyoming. The goal of the analysis is to identify which states are at risk, if at all, of lower water stock levels. Specifically, we hope to identify any states where more often than not, their water stock systems are at low levels or going towards that way.

### Data:

The data for this project comes for the [United Stated Department of Agriculture Department of Agriculture National Agricultural Statistics Service](https://quickstats.nass.usda.gov/). The data is recorded in a csv where you have the the state, the given week, the given water stock level, and the percentage of water stock systems at the level for that given week within that state. An example is depicted below.

<p align="middle">
  <img src="./inital_df.png" width="600">
</p>

From here, we proceed with individual processing as relevant for each objective. 

--------

## Seasonal Shifts:

When looking at the problem seasonally, we aim to capture the average percentage of water stock systems at each level for each season. The hope is that we do not notice any major change in percentage share of each level between seasons. For example, we would adequate to be at X% every season (and the same for every other stock level). This would imply that the differences between seasons do not impact the changes of water stock level percentages. 

### Results & Figures
<p align="middle">
  <img src="./Utah_seasonal.png" width="400">
  <img src="./Missouri_Seasonal_Redo2.png" width="400"> 
  <img src="./NewMexico_seasonal.png" width="400">
  <img src="./NorthDakota_seasonal.png" width="400">
  <img src="./Wyoming_seasonal.png" width="400">
</p>

The most important thing to notice from this image is that regardless of season, most water stock systems are, on average, at an adequate level. However there is some fluctuation to be noted. 

On a specific state level, we see that more of Utah's water stock systems are at short or super short during more extreme seasons like winter and summer at the cost of those at the amouunt at an adequate level going down. This also applies to North Dakota and Wyoming. For Missouri there is less of a change in percentages at given water stock levels across seasons. Though interestingly enough, we see that the surplus level increases past the short level in the summer, meaning that more water stock systems are at surplus during the summer in Missouri than are at short. Unfortunately, New Mexico seems to be at the greatest risk though, given that a greater portion of each season is at short/super short when compared to other states. But again, there is little fluctuation. 

Overall, seasons can have an effect, but they do not seem to drastically change the rank order of the water stock levels.

## Annual Percent Share

Next we looked at the average share of water stock levels per week for the past 7 years. The original dataset does not contain the exact information, so to accomplish this we created new arrays to store the necessary information.

### Average Annual Water Supply 

For each state, we isolated the supply level percents for each week of the year and summed the results; we then divided this by 100 multiplied by the total number of weeks in that year. This would give us the average percentage of each supply level shared with the other supply levels for each year. For instance, to calculate the adequate supply level for New Mexico, we used the following code:

<pre>
  <code>
  ad_percents = []
  
  for years in x:<br>  
        ad_percents.append(np.round(y_ad.loc[y_ad['Year']==years].sum(axis=0)['Percent Value']/
        df_nm.loc[df_nm['Year']==years].sum(axis=0)['Percent Value']*100,2))
  </code>
</pre>





## Most Common Weekly Levels

The dataset contains a weekly breakdown of each state’s waterstock level by percentage. The data in the charts reflects the level with the highest percentage for each week. This is useful for a general comparison of each state and the health of their waterstock levels on an annual basis. 

### Results and Figures

<p align="middle">
  <img src="./UT - Most Common Level - 2015-2022.jpg" width="400">
  <img src="./MO - Most Common Level -2015-2022.jpg" width="400">
  <img src="./NM - Most Common Level - 2015-2022.jpg" width="400">
  <img src="./ND - Most Common Level - 2015-2022.jpg" width="400">
  <img src="./WY - Most Common Level - 2015-2022.jpg" width="400">
</p>

Missouri has the most consistent water stock levels, as they did not record a single week where "adequate" was not the highest level. North Dakota had one of the most severe shortages in 2021, where "very short" was the highest level for over 60% of weeks in the year. The trends in the data suggest that prior to 2018, the majority of farms across each state had adequate amounts of water for their livestock. The majority of the problems for farms have come in the last four years, with all states except for Missouri having higher occurences of farms recording "short" or "very short" levels. Although many farms in each state had occurences of surpluses, "surplus" was never the level with th maximium number of occurences in a given week.
