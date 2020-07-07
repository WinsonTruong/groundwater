# Introduction 

Silicon Valley is well-known for being a center of technological innovation and economic prosperity, yet it is also one of the most polluted places in the United States. The image below is how far a cleaning chemical called trichloroethylene has spread across California. The image below shows the concentration of TCE across California!

![tce](https://github.com/WinsonTruong/groundwater/blob/master/images/tce_california.png)


The questions I'm asking are:

1. How effective has cleanup of superfund sites in Santa Clara been today? Is there still an association between superfund site locations and nearby groundwater quality?
2. Are certain populations disproportionately affected from superfund sites? Do more vulnerable groups (low-income, minority) tend to live closer to superfund sites?

# Notion Page
What's a superfund? Whats TCE? 
The background knowledge and workflow of this project is best documented [here!](https://www.notion.so/winsontruong/Silicon-Poisoned-Valley-8498e48a6d1e4915a68622b4d4c44388)


# Data
There are 3 data folders in this repository:

* gama_data contains groundwater data from the [California Open Data Platform](https://data.ca.gov/dataset/ground-water-water-quality-results/resource/5cef96fd-6f7b-4a83-ac83-aea62d437552)
* census_data was compiled thanks to the work at [Ro](https://www.notion.so/winsontruong/Metadata-f0b3594f84204713ba9499ecb0b0df1c)
* assorted_data contains various files such as income in Santa Clara County

Curious about the metadata? [Click here](https://www.notion.so/winsontruong/Metadata-f0b3594f84204713ba9499ecb0b0df1c)

# Notebooks
This project emphasizes EDA, visualizations, and feature selection to answers the questions using various tools such as Carto and random forest regressions.

# Findings
1. [TCE is everywhere but the Silicon Valley.](https://winsontruong.carto.com/builder/a7c91774-7c94-45fb-82dc-9d677740a439/embed)


2. More testing doesnt necessarily mean better groundwater.

![heatmap](https://github.com/WinsonTruong/groundwater/blob/master/images/testing_heatmap.png)


Three things to note:
1. ***Testing is effective!*** The focal point of the graph indicates that from around 2005-2008, the presence of 17-Dimethlyx and Acetaminophen hit a peak, before declining to seemingly normal levels. 
2. ***Testing is expensive.*** From 2004-2008, there is a large volume and variety of tests being conducted for the top 10 most commonly found chemicals, but *I **don't find it coincidental that the disappearance of testing aligned with the Great Recession.*** I use the black color scheme for 0 for a figurative blackout of testing could be related to the state's budget.
3. ***Testing is ambiguous**.* Unfortunately the amount of testing in 2013-2019 parallels initial levels in 2002. And further research is needed to be able to make any claims of groundwater poisoning leading to worse health outcomes as our analysis mainly observes frequency of testing as our dependent variable. Perhaps there is a possibility of false positives, false negatives, etc which would lead us in the direction of classification. Does more/less testing mean better groundwater conditions?

3. Testing volume is highly associated to marginalized races.

By implementing a random forest model for feature selection, here are the top 10 determinants for testing volume

![marginalized](https://github.com/WinsonTruong/groundwater/blob/master/images/top10features.png)



# Conclusion
1. Groundwater quality and public health today is still threatened by the microchip cleaning and rapid economic prosperity that the Valley has experienced. From our Carto maps, we saw the spread of TCE swarm inland California, while the Valley remained suspicioulsy TCE-free. The investigation of schools did not provide conclusive results.

2. While I wasn't able to fully investigate restoration efforts, I believe the observation that the sudden blackout in testing, probably due to the Great Recession, revealed how groundwater testing is victim to California's budget. 

3. Through the EDA process, we were able find a "large" sample size for the Fresno region even though we were unable to find a large sample size for California. A exploratory GLM revealed that there was statistical association between the number of Hispanic/Latino-identifying communities and number of testing.

# Further Studies

1. Identify the most life-threatening chemicals and see if I can use a classification methods such a k-nearest neighbors to see which chemicals are associated with the life-threatening ones. This might allow me to identify regions that should test for more dangerous chemicals if the "warning chemicals" are found!

2. A deeper data cleaning process to find more than 18 matches in our final groundwater dataset. Hopefully being able increase the volume, velocity, and voracity of the groundwater dataset will allow other scientists to find better results.
