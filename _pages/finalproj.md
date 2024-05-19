---
layout: archive
title: "Final Project"
permalink: /final-project/
author_profile: true
---

<h1>Exploring Spatial Correlation between Average Life Expectancy and Native American Population in Baltimore City</h1>

<h3> Introduction </h3>

<p> There is a significant gap in life expectancy between White and non-White people. With Native Americans having the lowest life expectancy (Fleck, 2023). This is connected to my GES 383 class, as for my final project I mapped out places of significance for Indigenous people in Baltimore city. By combining two different datasets, life expectancy per tract and population of Native Americans per tract, we can see whether or not there is a correlation between low life expectancy and indigeneity in Baltimore city. In creating these maps and performing a Moran’s I analysis of the data, we can see whether or not the percentage of Native American people per census tract and average life expectancy are spatially correlated. The significance of this research lies in understanding potential disparities in health outcomes among different demographic groups within an urban environment. The results of this research regardless of whether the null hypothesis is proved or disproved can still prove useful and create avenues for more research into the indigenous communities in Baltimore city in regards to public health research and policy-making. 
 </p>


<h3> Data and Methods </h3>
<p>The data for this study were obtained from the United States Census American Community Survey and the Centers for Disease Control and Prevention Life Expectancy Estimates. The dataset includes average life expectancy per census tract and the percentage of Native Americans per census tract in Baltimore City. Spatial analysis was conducted using Moran's I, a widely used statistical measure for assessing spatial autocorrelation in a geographic data visualization app called "GeoDa" (Anselin, 1995). The Moran's I calculates the degree of similarity between neighboring observations, making it suitable for detecting spatial patterns in demographic and health-related data.

Using the 2010 5-year ACS survey, I utilized the 'B03002' survey variable to extract both the total population of people per tract ('B03002_001') and the total population of Native Americans per tract ('B03002_005'). By dividing the latter by the former, I derived the percentage of Native Americans per tract. I read the Maryland life expectancy data from CDC into RStudio. Employing the 'filter' command, I refined this dataset to solely encompass information pertinent to Baltimore City, identified by the county FIPS code '510'. Seamlessly amalgamating these datasets, I executed a spatial join, utilizing the 'GEOID' column as the primary key. To ensure compatibility with mapping software I converted the life expectancy column from a string to a double. In GeoDa, I furthered your analysis by constructing a weights matrix file, with the 'percentage of Native Americans per tract' as the weight matrix variable and 'average life expectancy per tract' as the x variable. This laid the groundwork for a comprehensive exploration, including Moran's I test, to elucidate spatial clustering and significance, culminating in the creation of both cluster and significance maps within GeoDa.
 
 </p>
<h3>Analysis and Results </h3>
<p> The Moran's I value (Figure A) obtained from the analysis is 0.265, the interpretation of this result suggests a moderate degree of spatial autocorrelation between average life expectancy and the percentage of Native Americans in Baltimore City. However, the Moran’s I value exceeds the conventional significance level of 0.05, leading to the acceptance of the null hypothesis. Thus, there is no significant spatial correlation between these variables at the specified significance level. </p>


<h2> Below are six figures to illustrate the spatial distribution of the data. </h2>


<b> Figure A: Moran's I Graph showing how Native American population and Average Life Expectancy per census tract in Baltimore City are spatially correlated </b>

![Moran's I Graph](/images/moransi_graph.png)

A Moran's I Graph showing a value of 0.265. There is some correlation between average life expectancy and percentage of Native American people per tract in Baltimore City, but the correlation is not statistically significant enough.

<b> Figure B: Native American Population per census tract in Baltimore City </b>

![Native American Population per tract quantified using Natural Breaks](/images/nat_am_nat_break.png)


<b> Figure C: Average Life Expectancy per census tract in Baltimore City </b>

![Life Expectancy per tracts quantified using Natural Breaks](/images/lifeexp_nat_break.png)

<p> Jenks Natural Break Classification method was used to better understand the patterns and spread of the data. "Natural breaks" is a method used in cartography to classify and symbolize data based on natural groupings or patterns within the data itself.

In natural breaks classification, the data is divided into classes or groups in a way that minimizes the variance within each class while maximizing the variance between classes. The goal is to create classes that represent distinct groupings in the data, making it easier for map readers to interpret and understand the spatial distribution of the phenomenon being mapped (Schmitz, 2012).

This method is particularly useful when dealing with data that exhibits natural clustering or breaks, such as population density, income levels, or elevation. Instead of arbitrarily dividing the data into equal intervals or quantiles, natural breaks classification allows for more meaningful groupings that reflect the underlying patterns in the data.

When applied to symbology in maps, natural breaks classification helps to visually represent the data in a way that highlights the spatial patterns and variations, making it easier for map users to identify trends, outliers, and areas of interest. This can be done by using different colors, shades, or symbols to represent each class or group within the data. </p>

<b> Figure D: Map showing areas of Significant Spatial Correlation using the Moran's I test </b>

![LISA Significance Map](/images/lisa_sig_map.png) 

A map showing areas where the Moran's I value is less than or exceeds the p-value of 0.05, making certain areas less or more statistically significant. Census tracts with a p-values of 0.05, 0.01, and 0.001 indicate that there is a moderate, high, and significant  correlation-- respectively-- between average life expectancy and Native American population per census tract.


<b> Figure E: Cluster Map showing areas of strong and weak spatial correlation between Native American population and Average Life Expectancy per census tract in Baltimore City</b>

![LISA Cluster Map](/images/lisa_cluster_map.png) 

Cluster map showing where in Baltimore City there is strong and weak correlation. The dark red and dark blue patches show areas where there is high positive and high negative correlation between percentage of Native Americans and average life expectancy per tract. The light red and light blue patches on the map indicate where there is little correlation between the two variables. Grey areas show that there is no correlation at all between the two variables in those areas.


<b> Figure F: Map Comparing the Distribution of the Native American population and Average Life Expectancy per census tract in Baltimore City</b>

![Side-by-Side Map](/images/final_map_png.png) 

A side-by-side comparison of average life expectancy, percent Native American population per tract by tract, and a bivariete map showing how these two variables are spatially distributed. There appears to be an upside-down 'L' shape ('ꓶ') to the geographic data starting from Fallstaff going through Downtown and ending at Brooklyn, with Cross Country and North Roland Park neighborhoods having the most spatial correlation between average life expectancy and percentage of Native American population. Comparing this cluster map with the two natural breaks maps (Figure B and Figure C), we can see that the areas with a smaller population of Native American people tend to have a higher life expectancy. 

<h3> Conclusion </h3>
<p> Although the analysis did not find significant spatial correlation between average life expectancy and the percentage of Native Americans in Baltimore City, it is essential to interpret these results cautiously. The absence of significant correlation in all census tracts does not imply that the data is statistically insignificant in general. As we can see in the LISA Significance Map, Figure D, strong spatial correlation between the two variables exists in some census tracts and is absent from others. Nor does it imply the absence of health disparities or socio-economic factors influencing health outcomes within the population. Further research incorporating additional variables and considering potential confounders is warranted to provide a comprehensive understanding of health inequalities in urban settings. </p>

<h2>Reflection </h2>
<h3> On the Final Project </h3>
<p> This project provided valuable insights into spatial analysis techniques and their application in public health research. One notable challenge was the limited availability of detailed demographic data, which constrained the scope of our analysis. In future projects, accessing more comprehensive datasets and incorporating advanced spatial analysis techniques could enhance the robustness of the findings.  </p>
<h3>On the class overall </h3>
<p> In the class, I liked that we did hands-on exercises which had practical applications, because they facilitated a deeper understanding of spatial analysis methods and their implementation in real-world scenarios. I would have appreciated it if we had gone into more depth about the theoretical concepts behind the spatial analyses and other computer science concepts that we used in class.  </p>

<h3> Works Cited </h3>

<p>

Anselin, Luc. “Local indicators of Spatial Association— LISA.” Geographical Analysis, vol. 27, no. 2, Apr. 1995, pp. 93–115, https://doi.org/10.1111/j.1538-4632.1995.tb00338.x.

</p>



<p> 

CDC. “NVSS - United States Small-Area Life Expectancy Estimates Project.” Centers for Disease Control and Prevention, Centers for Disease Control and Prevention, 9 June 2020, www.cdc.gov/nchs/nvss/usaleep/usaleep.html.

</p>

<p> 
Fleck, Anna, and Felix Richter. “Infographic: Native Americans Still Face Significant Life Expectancy Gap.” Statista Daily Data, Statista, 9 Oct. 2023, www.statista.com/chart/30991/average-life-expectancy-in-the-united-states-by-racial-and-ethnic-groups/. 
</p>


<p>
 
Schmitz, Andy. “6.3 Data Classification.” Essentials of Geographic Information Systems v. 1.0, Saylor Academy, 2012, saylordotorg.github.io/text_essentials-of-geographic-information-systems/s10-03-data-classification.html.  

</p>


