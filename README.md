# MarsNews_Web_scraping

# This is a full webscraping exercise and a data analysis project based on the webscraping.
## Skills used in this project: collecting data, organizing data, storing data, analyzing data, and visually communicating insights
I accessed the Mars news site link (Source accessed on 27May2023:  https://static.bc-edx.com/data/web/mars_news/index.html) and performed the following actions:
-	identified the HTML elements on the webpage (eg, HTML tables, recurring elements like multiple news articles)
-	identified the id and class attributes of the HTM elements
-	extracted webpage information using automated browsing (using Splinter)
-	extracted webpage information using HTML parsing (using Beautiful Soup)

# Part 1: Scrape Titles and Preview Text from Mars News
The steps I followed to complete Part 1 and webscrape the Mars News page are listed below.
1.	Begin the Jupyter notebook with starter code.
2.	Use automated browsing to visit the Mars news site (https://static.bc-edx.com/data/web/mars_news/index.html). 
3.	Inspect the page to identify which elements to scrape. Use Chrome DevTools to identify which elements to scrape.  
4.	Create a Beautiful Soup object and use it to extract text elements from the website.
5.	Loop through the text elements.
6.	Extract the titles and preview text of the news articles that were scraped. 
7.	Store each title and preview pair in a dictionary.
8.	Give each dictionary two keys (title and preview) and store all the dictionaries in a Pyhton list.
9.	This is a list of news items extracted from the notebook:
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
