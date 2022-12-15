# Water Stock Analysis

-------

## Data:

The data for this project comes for the United Stated Department of Agriculture Department of Agriculture National Agricultural Statistics Service. The data is recorded in a csv where you have the the state, the given week, the given water stock level, and the percentage of water stock systems at the level for that given week within that state. An example is depicted below.

<p align="middle"> 
  <img src="/inital_df.png" width="600" />
</p>

From here, we proceed with individual processing as relevant for each objective. 



--------

## Seasonal Shifts:

When looking at the problem seasonally, we aim to capture the average percentage of water stock systems at each level for each season. The hope is that we do not notice any major change in percentage share of each level between seasons. For example, we would adequate to be at X% every season (and the same for every other stock level). This would imply that the differences between seasons do not impact the changes of water stock level percentages. 

### Results & Figures
<p align="middle">
  <img src="/Utah_seasonal.png" width="400" />
  <img src="/Missouri_seasonal.png" width="400" /> 
  <img src="/NewMexico_seasonal.png" width="400" />
  <img src="/NorthDakota_seasonal.png" width="400" />
  <img src="/Wyoming_seasonal.png" width="400" />
</p>

The most important thing to notice from this image is that regardless of season, most water stock systems are, on average, at an adequate level. However there is some fluctuation to be noted. 

On a specific state level, we see that more Missouri water stock systems are at a surplus level in the summer than are in short level which is different from all other seasons.
