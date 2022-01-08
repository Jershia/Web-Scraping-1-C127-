# Web Scraping 1
* We scraped the stars data from Nasa’s site

 ## Used
  * Usage of selenium
  * Usage of Beautiful soup
  * Getting data from Html of a page

## Steps To Create A Live Image Prediction
  * *We created a virtual environment.*
  * *We installed the necessary libraries.*
  * *We imported the selenium and Beautiful soup in our code.*
  * *We also installed the chrome driver.*
  * *Then we opened the link we want to scrape using selenium.*
  * *We got all the tags from the table to get the data from it.*
  * *We imported the selenium and Beautiful soup in our code.*
  * *We found all the ul tags to get the data.*
  * *Then we found all the li tags.*
  * *We found that all the data is inside the anchor tags.*
  * *We code to loop the code 489 times.*

## Code is given below
### *Code for importing libraries :*
from selenium 
import webdriver 
from bs4 import BeautifulSoup 
import time
import csv
### *Code to start chromedriver:* 
START_URL = "https://exoplanets.nasa.gov/exoplanet-catalog/" 
browser = webdriver.Chrome("/path/to/chromedriver") 
browser.get(START_URL)
time.sleep(10)
### *Code to get all tages from the data :*
![image](https://user-images.githubusercontent.com/74312429/148648368-310f459d-3f7f-4f7f-9b84-6cb2b94dc29d.png)
### *Code to get ul tages from the data :*
soup = BeautifulSoup(browser.page_source, "html.parser")
for ul_tag in soup.find_all("ul", attrs={"class", "exoplanet"}):
### *Code to get li tages from the data :*
li_tags = ul_tag.find_all("li")
### *Code to find the data in anchor tags:*
temp_list = []
for index, li_tag in enumerate(li_tags): if index == 0:
temp_list.append(li_tag.find_all("a")[0].contents[0]) else:
try:
temp_list.append(li_tag.contents[0]) except:
temp_list.append("")

planet_data.append(temp_list)
### *Code for scrape():*
![image](https://user-images.githubusercontent.com/74312429/148648562-8e9074e2-7abc-4aaa-80f5-4aab7a474389.png)
