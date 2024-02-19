# DataJam Canada 2021 - _**TRACKS: A Trafficking Reporting and Compilation frameworK System:**_

## 1. Problem Statement

Transport of victims is a major component of human trafficking. According to [Human-Trafficking Corridors in Canada by The Canadian Centre to End Human Trafficking](https://www.canadiancentretoendhumantrafficking.ca/wp-content/uploads/2021/02/Human-Trafficking-Corridors-in-Canada-Report.pdf), moving victims routinely aids traffickers from being detected by law enforcement and disorients victims and impedes them from seeking help. There is a lack of user-friendly reporting systems in place for those working in the transportation industry who are likely to see trafficking activity and a lack of methods to identify common trafficking routes. For example Uber which has an emergency alert system for passengers but not for drivers; drivers must rely on hotlines to report incidents. This is not ideal and verba information is easily lost.

## 2. Objective

Domestic trafficking via ground transport is a serious problem in Canada. Our objective is therefore to propose a framework to facilitate reporting of trafficking suspicions by drivers. Collections of reports can then be used to gain insights on high-risk areas and routes for trafficking, aiding law enforment to catch perpetrators. 

## 3. Solution/Data use case description

TRACKS: A Trafficking Reporting and Compilation frameworK System

TRACKS has three components:
1. Using factors which indicate vulnerability to trafficking (poverty, indigenous population, unemployment and education level) together with existing trafficking data as ground truth, we identify regions with higher risk of trafficking activity {ADD ABT MODEL!!}
2. We use the geolocation data of the driver to identify their trip's region(s). If they are detected to be in a high risk region, a notification is sent to them to report trafficking suspicions via a short form based on [UNODC indicators of trafficking](https://www.unodc.org/pdf/HT_indicators_E_LOWRES.pdf). 
3. Data from the form such as location and date/timestamps is anonymized, collected and analyzed in order to refine our prediction algorithm. Our aim is to collaborate with law enforcement so this data can be used to identify trafficking cases. There is limited data which can be used to identify trafficking routes, and this framework provides a means to collect data useful for this purpose.

The framework is versatile and can be applied to different provinces or for interprovincial anti-trafficking initiatives by using different datasets to train the model. Ride-sharing services such as Uber are popular in other countries in addition to Canada, and our the framework can be applied internationally to promote reporting of trafficking suspicions among transportation companies. By modifying aspects such as factors indicating vulnerability to trafficking and training data, the framework can better reflect the needs of other countries. 

Our solution can be a stand-alone app or it can be integrated into existing apps. An advantage of having a stand-alone app is that we do not need to ask a private company for access to location data.

In this proof of concept, we used data for regions in Ontario for which data on incidents of trafficking is available, and focused only on these select regions. Data on the factors (poverty, indigenous population, unemployment and education level) and trafficking is available for other Canadian regions. A direction for future work is to train our model with a larger dataset including these regions. The trained model can then be applied to other regions for which trafficking data is not available. For a simple use case, we use GO transit coordinates as driver location input to our framework as these are potential origin or destination points, especially for victims travelling by public transport. In addition, origin-destination data for Uber trips is publicly available for Toronto (and other international cities), and by processing this data we can extend our use case testing.

## 4. Pitch

_A pitch of maximum 4 minutes._d

Hint: Recommended is to add here just link(s), for example to Youtube recording:

Example location: [link to video](https://www.youtube.com/watch?v=xUcB90b2HMs)

GitHub Limitations:
 - 100MB per file
 - 10GB per repository

## 5. Datasets

Location: [/datasets](datasets)

_A list of data sets, sources and challenges for the research project._
This would include:

- API access to required TAH data
- Access to other datasets (either through API or downloaded)
- Statements on data quality issues, transformations needed
- Container for new data generated for this research (i.e. through merging other data sets)

2016 Canada Census data is used here. Data was downloaded from the official site and relevant variables were extracted for regions of interest. Data was cleaned and formatted before using for modeling. The hierarchy of regions (e.g. Census subdivision, Census metropolitan areas) for which data is available varies among the datasets and therefore it was a challenge to find datasets with a matching system of regions for comparison. In certain cases, information for some regions was missing.
**Sources**:

Human Trafficking Incidents and Sexual Exploitation Incidents: 
[Statistics Canada. Table 35-10-0177-01  Incident-based crime statistics, by detailed violations, Canada, provinces, territories and Census Metropolitan Areas](https://www150.statcan.gc.ca/t1/tbl1/en/tv.action?pid=3510017701)

For this proof of concept, we looked at regions in Ontario for which human trafficking data is available.

Income: 
[Statistics Canada, 2016 Census of Population, Statistics Canada Catalogue no. 98-400-X2016133.](https://www12.statcan.gc.ca/census-recensement/2016/dp-pd/dt-td/Rp-eng.cfm?LANG=E&APATH=3&DETAIL=0&DIM=0&FL=A&FREE=0&GC=0&GID=0&GK=0&GRP=1&PID=111873&PRID=10&PTYPE=109445&S=0&SHOWALL=0&SUB=0&Temporal=2016&THEME=119&VID=0&VNAMEE=&VNAMEF=)

Aboriginal Population: [Statistics Canada, 2016 Census of Population, Statistics Canada Catalogue no. 98-400-X2016173.]( https://www12.statcan.gc.ca/census-recensement/2016/dp-pd/dt-td/Rp-eng.cfm?TABID=2&LANG=E&APATH=3&DETAIL=0&DIM=0&FL=A&FREE=0&GC=0&GID=1341753&GK=0&GRP=1&PID=111095&PRID=10&PTYPE=109445&S=0&SHOWALL=0&SUB=0&Temporal=2017&THEME=122&VID=0&VNAMEE=&VNAMEF=&D1=0&D2=0&D3=0&D4=0&D5=0&D6=0)

Employment & Education: [Statistics Canada, 2016 Census of Population, Statistics Canada Catalogue no. 98-400-X2016284.](https://www12.statcan.gc.ca/census-recensement/2016/dp-pd/dt-td/Rp-eng.cfm?TABID=2&LANG=E&APATH=3&DETAIL=0&DIM=0&FL=A&FREE=0&GC=3515&GID=1259598&GK=2&GRP=1&PID=111848&PRID=10&PTYPE=109445&S=0&SHOWALL=0&SUB=0&Temporal=2017&THEME=124&VID=0&VNAMEE=&VNAMEF=&D1=0&D2=0&D3=0&D4=0&D5=0&D6=0)

Latitude-Longitude Coordinates for Ontario Regions: https://developer.mapquest.com/documentation/tools/latitude-longitude-finder/

Latitude-Longitude Coordinates for GO Transit Stops used in Use Case: http://www.metrolinx.com/en/aboutus/opendata/default.aspx

Additional data found for future use:

Origin-Destination of Drivers - Record of Uber Trips: https://movement.uber.com/?lang=en-CA

Detailed Record of Uber Trips: https://www.kaggle.com/fivethirtyeight/uber-pickups-in-new-york-city

## 6. Project Code

Location: [/project](project)

This would include the following:

- Data transformations, merging & quality assurance
- Model related code (projection, prediction, correlation etc.)
- User Interface code

## 7. Additional docs (Optional)

Location: [/docs](docs)

- PowerPoint presentation
- Flayers
- Additional videos/demo
- Protocols
- Guides
