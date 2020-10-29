# API-challenge
API Homework
Autumn Demonet

## Reflection:
Starting this homework assignment was rather daunting, but quickly proved to be a rewarding once I got my .gitnore set up correctly. In combining what I learned in the previous units with the new tool kit of API calls, I feel that I now have access to a wealth of data as well as a rudimentary skill set in manipulating that data into compelling visualizations.

I would like to offer a few observations from my work:

### Observation the First
I can now confirm that, as my instructors have repeatedly assured me, the hardest part of creating an API call is making sure to pull the correct information from the documentation (especially for the Google APIs - I learned to stay vigilant about "keyword" vs. "type" calls in the Google Places API call). One issue that I ran into when appending the values from the API call into my empty list was that directly appending was not working. My solution for this was to create a set of temporary values that could hold the data long enough to append it to the appropriate list before the for loop started over. For example, to append the city names to City = [], I created a value cn = data["name"] in a for loop and then used City.append(cn) to transfer the city name into the list. This was also a great opportunity to work with a try/except, because not all calls returned valid data and therefore needed to be skipped over.

### Observation the Second
In looking at the graphs created with Matplotlib, the most striking visualization is the plot of the relationship between Latitude and Max Temp, which takes the clear form of a parabola. It is appropriate here to divide the Latitude values by Northern and Southern hemisphere and investigate the plots that are conceived from that division. Unsurprisingly, there is a strong negative correlation between Latitude and Max Temp (r-squared = 0.76), which is to say that the further one is from the equator, the colder it will be. As expected, the inverse is true of the relationship between Latitude and Max Temp in the Southern Hemisphere, though it is worth noting that in my plots, this correlation is much weaker (r-squared = 0.40). This could be explained by the fact that the Northern Hemisphere accounts for 405/547 datapoints and the Southern Hemisphere for only 159/547. It would be worth investigating if more datapoints for the Southern Hemisphere would strengthen this correlation.

### Observation the Third
gmaps is fun. Though initially intimidated by it, I enjoyed using this tool to visualize points on a map (this time with a view on humidity levels across the globe). The major issue that I ran into in creating these maps was caused by a single one of my datapoints in the filtered hotel_df, which did not return a hotel within the given radius of 5000. In order to resolve this issue, I had to revisit the try/except structure to skip calls that returned no values. I found it interesting that given my constraints of a Maximum Temperature between 70 and 80 degrees, a Wind Speed of less than 5 mph, no clouds, and Humidity less than 70%, six out of seven of the ideal locations were all between latitude lines 17 and 26, with the exception of Esperance in Australia, which is the only ideal vacation city located in the Southern Hemisphere. Personally, I think that these must really be some ideal vacation spots, as they are all close to or fall within the Bean Belt and I love a good single-origin coffee!

