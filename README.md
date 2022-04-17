# 311project
Using 311 open data to dig around


Just digging around using https://hwangnyc.medium.com/using-r-to-access-311-service-request-from-nyc-open-data-using-socrata-open-data-api-and-the-83de00327a8c as a guide to start. 

categories of complaints to the NYPD includes: 
 [1] "Illegal Parking"             "Blocked Driveway"           
 [3] "Abandoned Vehicle"           "Animal-Abuse"               
 [5] "Graffiti"                    "Noise - Vehicle"            
 [7] "Noise - Commercial"          "Noise - Residential"        
 [9] "Noise - Street/Sidewalk"     "Urinating in Public"        
[11] "Encampment"                  "Illegal Fireworks"          
[13] "Panhandling"                 "Non-Emergency Police Matter"
[15] "Drug Activity"               "Drinking"                   
[17] "Traffic"                     "Bike/Roller/Skate Chronic"  
[19] "Squeegee"                    "Noise - House of Worship"   
[21] "Noise - Park"                "Disorderly Youth"           
[23] "Posting Advertisement"       "Mass Gathering Complaint" 

# libraries needed 

packages - RSocrata, ggplot2

# code so far on abandoned vehicles 
NYPD <- read.socrata("https://data.cityofnewyork.us/resource/erm2-nwe9.json?$where=created_date between '2021-01-01T12:00:00' and '2022-01-31T23:00:00' and agency = 'NYPD' and complaint_type = 'Abandoned Vehicle'")

Provides essentially 2021 and YTD 2022 Abandoned vehicle reports. 

# simple bar chart as the following

ggplot(data= NYPD, aes(x = borough)) + geom_bar() 

![image](https://user-images.githubusercontent.com/14792681/151902839-f40eb8a3-7567-4f2e-be3c-c77857514a4b.png)
