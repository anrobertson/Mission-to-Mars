# Mission-to-Mars

## Overview
For this week, the job I had set in place was to help Robin scrape, organize, analyze, and visualize the data. This involved scraping the titles and preview texts from the Mars news articles as well as scrape and analyze Mars weather data.

## Resources
Software used:
 * Python
 * Jupyter Notebook
 * BeautifulSoup
 * Pandas
 * Matplotlib

## Results
In the first deliverable, my job was to scrape the titles and preview text from the Mars News. I then created a Beautiful Soup object and extarcted the text elements from the website.

```
# Extract all the text elements
text = news_soup.find_all('div', class_= 'list_text')

print(text)
```
With the results in hand, I created an empty list to store the content and created dictionaries by using a for loop.
```
# Loop through the text elements
# Extract the title and preview text from the elements
# Store each title and preview pair in a dictionary
# Add the dictionary to the list
slide_elem = news_soup.find_all('div', class_= 'list_text')

for elem in slide_elem:
    mars_data = {"title":"", "preview":""}
    title = elem.find('div', class_= 'content_title').text
    preview = elem.find('div', class_= 'article_teaser_body').text
    mars_data["title"] = title
    mars_data["preview"] = preview
    mars_preview_pairs.append(mars_data)
```
After scraping this web page, I moved on to the Mars Weather Data. Once, again I extracted the data but instead of finding a list, I used the 'table' class. Once using my for loop to gather the header rows, I created a Pandas DataFrame and changed the data types for the analysis. At this point, I was ready to create the graphs.


