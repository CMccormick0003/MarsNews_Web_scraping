# MarsNews_Web_scraping

# This is a webscraping exercise and a data analysis project.
## Skills used in this project: collecting data, organizing data, storing data, analyzing data, and visually communicating insights

# Part 1: Scrape Titles and Preview Text from Mars News
I accessed the Mars news site link (Source accessed on 27May2023:  https://static.bc-edx.com/data/web/mars_news/index.html) and performed the following actions:
-	identified the HTML elements on the webpage (eg, recurring elements like multiple news articles)
-	identified the id and class attributes of the HTM elements
-	extracted webpage information using automated browsing (using Splinter)
-	extracted webpage information using HTML parsing (using Beautiful Soup)

1.	Use automated browsing to visit the Mars news site (https://static.bc-edx.com/data/web/mars_news/index.html). 
2.	Inspect the page to identify which elements to scrape. Use Chrome DevTools to identify which elements to scrape.  
3.	Create a Beautiful Soup object and use it to extract text elements from the website.
4.	Loop through the text elements.
5.	Extract the titles and preview text of the news articles that were scraped. 
6.	Store each title and preview pair in a dictionary.
7.	Give each dictionary two keys (title and preview) and store all the dictionaries in a Pyhton list.
8.	Print the list of news items in the notebook:
---------------------------------------
[{'title': "NASA's MAVEN Observes Martian Light Show Caused by Major Solar Storm",
  'preview': 'For the first time in its eight years orbiting Mars, NASA’s MAVEN mission witnessed two different types of ultraviolet aurorae simultaneously, the result of solar storms that began on Aug. 27.'},
 {'title': "NASA Prepares to Say 'Farewell' to InSight Spacecraft",
  'preview': 'A closer look at what goes into wrapping up the mission as the spacecraft’s power supply continues to dwindle.'},
 {'title': 'NASA and ESA Agree on Next Steps to Return Mars Samples to Earth',
  'preview': 'The agency’s Perseverance rover will establish the first sample depot on Mars.'},
 {'title': "NASA's InSight Lander Detects Stunning Meteoroid Impact on Mars",
  'preview': 'The agency’s lander felt the ground shake during the impact while cameras aboard the Mars Reconnaissance Orbiter spotted the yawning new crater from space.'},
 {'title': 'NASA To Host Briefing on InSight, Mars Reconnaissance Orbiter Findings',
  'preview': 'Scientists from two Mars missions will discuss how they combined images and data for a major finding on the Red Planet.'},
 {'title': 'Why NASA Is Trying To Crash Land on Mars',
  'preview': 'Like a car’s crumple zone, the experimental SHIELD lander is designed to absorb a hard impact.'},
 {'title': 'Curiosity Mars Rover Reaches Long-Awaited Salty Region',
  'preview': 'After years of climbing, the Mars rover has arrived at a special region believed to have formed as Mars’ climate was drying.'},
 {'title': 'Mars Mission Shields Up for Tests',
  'preview': 'Protecting Mars Sample Return spacecraft from micrometeorites requires high-caliber work.'},
 {'title': "NASA's InSight Waits Out Dust Storm",
  'preview': 'InSight’s team is taking steps to help the solar-powered lander continue operating for as long as possible.'},
 {'title': "NASA's InSight 'Hears' Its First Meteoroid Impacts on Mars",
  'preview': 'The Mars lander’s seismometer has picked up vibrations from four separate impacts in the past two years.'},
 {'title': "NASA's Perseverance Rover Investigates Geologically Rich Mars Terrain",
  'preview': 'The latest findings provide greater detail on a region of the Red Planet that has a watery past and is yielding promising samples for the NASA-ESA Mars Sample Return campaign.'},
 {'title': 'NASA to Host Briefing on Perseverance Mars Rover Mission Operations',
  'preview': 'Members of the mission will discuss the rover’s activities as it gathers samples in an ancient river delta.'},
 {'title': "NASA's Perseverance Makes New Discoveries in Mars' Jezero Crater",
  'preview': 'The rover found that Jezero Crater’s floor is made up of volcanic rocks that have interacted with water.'},
 {'title': "10 Years Since Landing, NASA's Curiosity Mars Rover Still Has Drive",
  'preview': 'Despite signs of wear, the intrepid spacecraft is about to start an exciting new chapter of its mission as it climbs a Martian mountain.'},
 {'title': "SAM's Top 5 Discoveries Aboard NASA's Curiosity Rover at Mars",
  'preview': '“Selfie” of the Curiosity rover with inset showing the SAM instrument prior to installation on the rover.'}]
  
# Part 2: Scrape and Analyze Mars Weather Data
I accessed the Mars Temperature Data site link (Source accessed on 27May2023:  https://static.bc-edx.com/data/web/mars_facts/temperature.html) and performed the following actions:
-	identified the HTML elements on the webpage (eg, HTML table)
-	extracted webpage information using HTML parsing (using Beautiful Soup)
-	analyzed data using Pandas
-	graphed data using matplotlib

1.	Use automated browsing to visit the Mars Temperature Data site (https://static.bc-edx.com/data/web/mars_facts/temperature.html). 
2.	Inspect the page to identify which elements to scrape. Use Chrome DevTools to identify which elements to scrape.  
3.	Create a Beautiful Soup object and use it to extract the data in the HTML table.
4.	Assemble the scraped data into a Pandas DataFrame. The columns should have the same headings as the table on the website. 
5.	Column headings in the data table are described below:
- id: identification number of a single transmission from the Curiosity rover
- terrestrial_date: date on Earth
- sol: number of elapsed sols (Martian days) since Curiosity landed on Mars
- ls: solar longitude
- month: Martian month
- min_temp: minimum temperature, in Celsius, of a single Martian day (sol)
- pressure: atmospheric pressure at Curiosity's location
6.	Examine the data types that are currently associated with each column. 
7.	Convert some of the data types from “object” to datetime, int or float before using them in data analyses. 
8.	Analyze the dataset by using Pandas functions.
9.	Export the mars_weather.csv. 

## Analysis of Mars weather
### How many months exist on Mars?
 ![image](https://github.com/CMccormick0003/MarsNews_Web_scraping/assets/120672518/44357d65-b87c-40fe-bb16-52fe0db511c2)

### How many Martian (and not Earth) days worth of data exist in the scraped dataset?
1867 Martian days
This was obtained from the following code:
days_of_Mars_data = df['sol'].nunique()

### What is the average low temperature by month?
average_low_temp_per_Mars_month = pd.DataFrame(df.groupby('month')['min_temp'].mean())

![image](https://github.com/CMccormick0003/MarsNews_Web_scraping/assets/120672518/3fdc22f9-0af5-47c9-8c7b-fef42d195722)

Plot the results as a bar chart.

![image](https://github.com/CMccormick0003/MarsNews_Web_scraping/assets/120672518/9cc9b146-74a5-4b0e-ab2a-71755ccd3459)


### What are the coldest and the warmest months on Mars (at the location of Curiosity)? 
Find the average minimum daily temperature for all of the months.
temp_curiosity_month = df.groupby('month')['min_temp'].mean()
temp_curiosity_month.sort_values().plot(kind='bar',rot=0)
Average Coldest Temperature:  Month 3, - 83.307292 °C
Average Warmest Temperature:  Month 8, - 68.382979 °C

![image](https://github.com/CMccormick0003/MarsNews_Web_scraping/assets/120672518/3707a157-514e-4ef1-b429-50cc53da19f0)

### Which months have the lowest and the highest atmospheric pressure on Mars?
Find the average daily atmospheric pressure of all the months.
average_pressure_per_Mars_month = pd.DataFrame(df.groupby('month')['pressure'].mean())
Average Lowest Pressure:  Month 6, 745.054422 pascals
Average Highest Pressure:  Month 9, 913.305970 pascals
Plot the results as a bar chart.

![image](https://github.com/CMccormick0003/MarsNews_Web_scraping/assets/120672518/1026b663-6ffd-4390-8ebd-f071e56e4656)

### About how many terrestrial (Earth) days exist in a Martian year?
Consider how many days elapse on Earth in the time that Mars circles the Sun once.
df.min_temp.plot()
plt.xlabel("Number of Terrestrial Days on Mars")
plt.ylabel('Minimum Temperature (C)')
plt.show

Visually estimate the result by plotting the daily minimum temperature.

![image](https://github.com/CMccormick0003/MarsNews_Web_scraping/assets/120672518/70f0e29f-a588-4141-848e-c12f0fb3a6b8)

Export the DataFrame to a CSV file.

Mars Data Source:
Mars Weather data shared on data.world by The Pudding, with the following information:
What is this?: Data representing the weather conditions on Mars from Sol 1 (August 7, 2012 on Earth) to Sol 1895 (February 27, 2018 on Earth).
Source(s) & Methodology: This data was measured and transmitted via the Rover Environmental Monitoring Station (REMS) on-board the Curiosity Rover. The data was made publicly available by NASA’s Mars Science Laboratory and the Centro de Astrobiología (CSIC-INTA). 

