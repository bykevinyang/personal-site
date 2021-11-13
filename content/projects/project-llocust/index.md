+++
title = "Project L.L.O.C.U.S.T."
date = 2021-03-29

[taxonomies]
categories = ["Hackathon", "Software"]
+++

# Background

Project L.L.O.C.U.S.T. is a hackathon project for NASA's 2020 Space Apps Challenge. It won Global Winner as the project with the most potential to improve life on Earth or in the universe. Original submission <a href="https://2020.spaceappschallenge.org/challenges/inform/automated-detection-hazards/teams/project-llocust-1/project">documentation

<p class="has-text-align-center" style="font-size:23px"><strong>-- <a href="https://www.youtube.com/watch?v=RI2gLdX9DAE">Video Demo</a> --</strong></p>

# Summary

Project L.L.O.C.U.S.T. detects and predicts locust' whereabouts as well as forecasts their movements in vulnerable areas. Using a machine learning model trained on NASA's satellite data of wind, humidity, surface temperatures, and vegetation index, —all of which are factors that promote locust population—we attune L.L.O.C.U.S.T. to create a heat map of areas that are most at risk of locust infestation. Through the use of an interactive, AI-powered, user-friendly website, farmers, city-officials, and businesses alike are able to view our model's detections and forecasts in the form of an interactive map.
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3>How&nbsp;We&nbsp;Addressed This Challenge</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Our team has developed a machine learning model that was trained on satellite data of wind, humidity, surface temperatures, and vegetation index from the SMAP and Terra (MODIS instrument, ASTER instrument) satellites. The final product is shown as a website map that helps detect and assess current risk levels and forecast locust invasions given a location and time.</p>
<!-- /wp:paragraph -->

<img src="https://sa-2019.s3.amazonaws.com/media/images/97945216-ef2a-4dfe-ae25-e5c8b931804e.max-1000x1000.jpg" alt="" width="750" height="505"/>

Project L.L.O.C.U.S.T. is vital for maintaining food security. When swarming, locusts can consume as much food 35,000 people could,&nbsp;<em>per day</em>. Put in context of where locusts are most abundant, such as East Africa and Northern India, such detriment threatens the livelihood of ordinary people and businesses. When the locust breeding season begins, farmers are only notified of an approaching swarm when they come face to face with it on their farmland. This leaves them with little time to prepare, the only option being watching the locusts consume their one source of income.

<img src="https://sa-2019.s3.amazonaws.com/media/images/f2a68b76-33ff-496f-83a0-87b5faa02ccd.max-1000x1000.png" alt="" width="750" height="495"/>

However, using L.L.O.C.U.S.T., farmers are not only able to see whether or not that they are at risk of locust infestation, they can also get a weather-like forecast of where the locust are most likely to fly next.

<img src="https://sa-2019.s3.amazonaws.com/media/images/ea2b99ea-1846-4a13-9aa8-c653b5644078.max-1000x1000.png" alt="" width="750" height="495"/>

To use L.L.O.C.U.S.T., all that is needed to be done is to specify your geographical location. From there, L.L.O.C.U.S.T. will pull satellite imagery from NASA’s Terra (MODIS instrument, ASTER instrument) and SMAP satellites, looking specifically at humidity, soil moisture, temperature, elevation and vegetation. This data will then be fed into our model, outputting a heat map displaying how likely a swarm will crop up around your current location.

Besides that, L.L.O.C.U.S.T. also utilizes wind data from NOAA to calculate where a swarm will most likely go to next. This portion of the project relies on the fact that locust swarms fly with the wind and do not fly around randomly. This allows us to project an area of swarming, similar to how a meteorologist could predict the path of a hurricane.

All in all, Project L.L.O.C.U.S.T. hopes to give insight into locust swarming, giving city officials extra time in planning and preparing for an infestation, strengthening local agriculture and giving farmers the much needed chance in protecting their crops, saving billions in the long run.

## What Inspired your team to choose this challenge?

We felt inspired to contribute to the growing relevance of using Artificial Intelligence in addressing modern world problems.

With climate change creating atmospheric discord and fires raging across the world, our team knew that the best use of our skill sets would be training and applying a ML model to detect hazards.

However, when researching hazards to focus the project about, our team learned that many of the “common” hazards that appear on news have already had extensive, well-documented research. This left us wanting to choose a hazard that was non-mainstream, a hazard that is increasingly relevant yet under the radar of the media and the press. This narrowed our search directly to locusts, which over the course of the late spring to early summer, devastated Eastern Africa, the Arabian Peninsula, and Northern India.

<img src="https://sa-2019.s3.amazonaws.com/media/images/74b14eef-3ea4-400f-ad42-fd91a36fcbbb.max-1000x1000.jpg" alt="" width="750" height="500"/>

By some estimates, more than $8.5 billion worth of damages have occurred in Eastern Africa alone, causing 20 million people to go food insecure according to the&nbsp;<a href="https://www.worldbank.org/en/news/factsheet/2020/04/27/the-locust-crisis-the-world-banks-response#:~:text=of%20the%20outbreak%3F-,A.,Africa%20region%2C%20Djibouti%20and%20Yemen.">World Bank</a>&nbsp;and&nbsp;<a href="https://www.nature.com/articles/d41586-020-00692-3">Nature&nbsp;</a>respectively. However, there has been little press coverage on the plaque, sitting under the shadow of COVID-19. What is most alarming is that there has been an&nbsp;<a href="https://www.carbonbrief.org/qa-are-the-2019-20-locust-swarms-linked-to-climate-change">8,000-fold increase</a>&nbsp;in locust breeding this past year, caused by rare conditions that climate change have amplified.</p>

## What was your approach to developing this project?

Our approach to the project can be broken down into three steps.

<img src="http://bykevinyang.com/wp-content/uploads/Locust_Schematic_White-1-1002x1024.png" alt="" class="wp-image-2431" width="752" height="768"/>

The first step was to get the data required to train our model. To do this, we created a data pipeline that pulled satellite imagery from NASA’s worldview servers. The specific satellites we pulled from are NASA’s Terra (MODIS instrument, ASTER instrument) and SMAP satellites. From there, we did data preparation on the satellite images, essentially cropping them to the specific coordinates of known swarm locations (the swarm locations were pulled from the&nbsp;<a href="https://locust-hub-hqfao.hub.arcgis.com/">FAO’s Locust Hub</a>). As well, we created a Python script that will create random coordinates in areas that do not have locust infestation to better strengthen the model.

The second step in our approach was training the risk prediction model and creating the swarm “weather” forecast. To train, we first downloaded, processed and stored the dataset from various sources and satellite data. We stored the pixel values as hex values in the dataframe for easy storing and manipulation and then we converted the hex values to RGB values and used them for model training as well as testing.

In the third step, we focused our efforts on being able to concisely and clearly display the information about our model and forecast output. To do this, we created a website which shows our results on a multilayer map. The site is designed to allow users to toggle various layers and visualize locust swarms alongside insightful ancillary data such as population density and farmland. We adapted an existing wind-prediction model to predict future locust movement patterns and visualize them in a clear way.

<img src="https://sa-2019.s3.amazonaws.com/media/images/d7cd3c63-710e-477d-a271-342d5da0de99.max-1000x1000.png" alt="" width="980" height="543"/>

## What tools, coding languages, hardware, software did you use to develop your project?

We used Python to create a data pipeline, allowing us to collect, manipulate and store satellite imagery using libraries such as Pandas and Raster.io. After having the data in the right format, we then used the Sklearn machine learning library to create a model to predict whether a locust would be present at a given place and time given the features such soil moisture, temperature, humidity, elevation, and vegetation.

Since the downloading and processing of satellite images in TIFF format was computationally and time intensive, we decided to collect a decent amount of data for locations where the locusts invasion happened and also locations where it did not happen. After training, our Random Forest model and SVC model had an accuracy of 100% during testing (we suspect this is due to the limited amount of data we had&nbsp;around 200 samples for testing). Then this model was used by the frontend app to display the likelihood of locust infestation in a certain location.

The visual frontend part of the website was created using the Leaflet.JS mapping library. The wind simulation was created using a heavily modified version of the leaflet-velocity wind rendering library to project the future movement patterns of locust swarms. Heatmaps were rendered on the map using Leaflet.Heat to show population density and our predictions for where locust outbreaks could occur.<

## What problems and achievements did your team have?

### Problems:

One of the biggest challenges that our team encountered was obtaining and formatting the data in a way that was usable while identifying the most useful data points in order to keep the size of our data set manageable. In total, we spent 12+ hours debugging and figuring out how to efficiently pull satellite imagery from NASA’s worldview database. Besides that, no one was prepared for how difficult it is to work with satellite imagery. Although some of our team members have worked with creating image-based models, satellite imagery and the many obscure, foreign formats they are in, it was not only excruciatingly hard to work with, but cost the team a lot in time.

One other challenge was not finding out about a bug with the EOSDIS Worldview website until it was that we cannot obtain snapshots of layers where the data is Monthly, 6-Day.8-Day..etc and is not a single day data for most layers that we wanted. But we found alternative layers that did the work after a long time debugging the data and model, and talking to SMEs over rocketchat.

We also experienced difficulties with modifying the wind model for our predictive purposes, but at the end, we managed to create a powerful visualization tool that can be used by citizens and researchers alike.

We wanted to add a feature to forecast the economic cost a certain locust swarm could cause based on its predicted path. However, we were only able to create mockup data on the map to showcase that feature because we were time constrained.

### Achievements

Throughout the weekend, our team struggled with getting actual data which we could use to train the model. After many hours of debugging and collaboration between teammates and mentors, we eventually finished the data pipeline that pulls data from NASA’s world view servers and prepares them for use in model training.

Another achievement was adding in most, if not all, the features on the website. As well, we were able to train an entire model on the data we collected and it worked out pretty well.

Last but not the least, at the beginning of the hackathon, our team struggled to get an idea off the ground. We came up with many good ideas such as heat wave prediction, asteroid impact detection, iceberg breaking classifier, and applying machine vision on other planets, most specifically Mars for studying Dust Storms.

Sadly, all these ideas ended with nothing due to complications in acquiring data, fitting challenge requirements, and time limit of the hackathon. However in the end, we were able to come up with a problem idea that had accessible data allowing us to create a AI based interactive solution.

All in all, this weekend has had its ups and downs but we managed to overcome our challenges through sheer teamwork and commitment, allowing us to create a powerful data tool that can be used by anyone to predict locust attacks.

### How We Used Space Agency Data in This Project

We requested images from NASA"s Terra and SMAP satellites based off of specific coordinates from the Locust Swarm dataset (supplied by FAO) and then using Raster.io, we saved the binary data received to a TIFF file. We then extracted the values of pixels at the specific coordinates of Locust swarms and non-swarm location as hex value. We then converted those values to RGB for further use during training and testing.

**We used the following layers:**

<ol><li>SMAP_L4_Analyzed_Surface_Soil_Moisture (Soil_Moisture)</li><li>ASTER_GDEM_Color_Index (Elevation)</li><li>SMAP_L4_Soil_Temperature_Layer_1 (Soil Temp)</li><li>MODIS_Terra_NDVI_8Day</li></ol>

<p><a href="https://worldview.earthdata.nasa.gov/">NASA Worldview</a></p>

<p><a href="https://github.com/nasa/spaceapps-phenomena_detection">Space Apps Phenomena Detection</a></p>

## Project Demo

<a href="https://youtu.be/RI2gLdX9DAE"><strong>Video</strong></a>

<p><a href="https://determined-keller-5cbae8.netlify.app/"><strong>Live Website</strong></a></p>

<p><a href="https://github.com/kevin200617/Project-L.O.C.U.S.T/"><strong>Github</strong></a></p>

<h2>Data &amp; Resources</h2>

### Articles

<ul><li><a href="https://locust-hub-hqfao.hub.arcgis.com/datasets/swarms-1?showData=true">Locust Hub Swarm Data&nbsp;</a>- FAO</li><li><a href="https://iridl.ldeo.columbia.edu/maproom/Food_Security/Locusts/index.html">Locust Food Insecurity Database</a>&nbsp;- Columbia’s International Research Institutes for Climate and Society</li><li><a href="https://nomads.ncep.noaa.gov/">Operational Model Archive and Distribution System</a>&nbsp;- NOAA</li><li><a href="https://worldview.earthdata.nasa.gov/">Worldview&nbsp;</a>- NASA</li><li><a href="https://github.com/nasa/spaceapps-phenomena_detection">Spaceapps Phenomena Detection Github&nbsp;</a>- NASA</li><li><a href="https://www.esa.int/Applications/Observing_the_Earth/Satellites_forewarn_of_locust_plagues">Satellites forewarn of locust plagues&nbsp;</a>&nbsp;- ESA</li></ul>

<h4><strong>Videos:</strong></h4>

<ul><li><a href="https://www.youtube.com/watch?v=Z6bDrgQE-1U">Why This Year's Locust Invasion Is Setting Off Global Panic</a>&nbsp;- Vice&nbsp;</li><li><a href="https://www.youtube.com/watch?v=aQ804ztWPNs">The Great North American Locust Plague</a>&nbsp;- Minute Earth&nbsp;</li><li><a href="https://www.youtube.com/watch?v=xeHukQ6Ux1k">Fighting a locust plague amid Covid-19 in east Africa</a>&nbsp;- The Guardian</li><li><a href="https://www.youtube.com/watch?v=Vo61TiAGwhk&amp;t=43s">Why locusts are descending on East Africa</a>&nbsp;- Vox</li></ul>