# Stream Gauge Meta Data

Stream gauge discharge data in Asheville, North Carolina came from the United States Geographical Survey’s (USGS) National Water Information System (NWIS). We were able to pull this dataset into R using the dataretreival package, function readNWISdv, which lets you simply put the specific USGS code for the area we were interested in looking more closely at, ours being the French Broad River, 03451500. There were multiple parameters available for this site including discharge, precipitation, pH, stream level, etc. By identifying the USGS code as well as the specific codes for the parameters we wanted to look at (i.e., discharge data) we were able to pull in corresponding data for the last 60 years. Because discharge data is recorded daily, we had records of every day from 1963 to 2021. The pulled dataset included the agency (USGS), the site number, the date, and the amount of discharge in cubic feet per second.

Code to pull data:
AshDischarge <- readNWISdv(siteNumbers = "03451500",
                     parameterCd = "00060", # discharge (ft3/s)
                     startDate = "1963-10-01", 
                     endDate = "2021-12-31") #complete water years