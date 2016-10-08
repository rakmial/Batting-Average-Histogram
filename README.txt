***
SUMMARY-----

This interactive and animated plot shows a number of summary statistics based on the individual statistics of a number of baseball players. The graph shows left-handed players to consistently outperform right-handed players across different heights at batting average as well as home runs, though home runs seem to be affected more by the player's height.

***
DESIGN -----

The first important design decision to be made involved players with a 0.000 batting average. Nearly 23% of observations had this value. When I first made my plot as a histogram, the 0.00 batting average observations ruined the scale of the chart - the y-axis must be stretched greatly to show the bin of magnitude 266, and entirety of non-zero observations fit into a domain between 0.066 and 0.328, leaving a great white gap between 0.000 and 0.066.

It was possible to design the story around this feature of the data - the fact that more than a fifth of the players in the dataset had never hit a single pitch is interesting, but it wasn't a story I was interested in telling. Using R to subset the data, I removed observations of players with a batting average of 0.000.

I also decided to remove outlier heights, below 68 and above 76, because they did not feature enough information about left-handed players to make the summary statistics rigorous (ie, the "67 L median" summary entry only featured two players, one that hit 228 home runs and another that hit zero). 

After cleaning the data, I realized that I had two categorical variables and two continuous variables that I wanted to explore. Finding a plot that would allow me to explore these variables without making it look busy or unnecessarily complicated was difficult, but eventually I settled on a double y-axis design that was fairly elegant.

***
FEEDBACK -----

My next changes were made after receiving feedback from roommates. They noted that my original settings for the font in the tooltips made it hard to read, and player names and values for the tallest bins sometimes clipped out of the window. I altered settings to shrink the font and margins, grouping the names more tightly. However, this made the names harder to read. Eventually I settled on a small-caps lettering theme that made the smaller font/margin readable even when compressed closely. I changed my x- and y-axis labels to match the tooltip as well.

I was pleased that my roommates had a similar experience with the chart as I did, wondering aloud who Dean Chance and Rod Carew were. Luckily, I had already read their wikis and could tell them. However, that kind of narrative guiding would work well paired with an article about batting averages, particularly if they specifically mentioned Chance and Carew.

For the third revision of my graphic, I responded to feedback from a Udacity coach, adding some explanatory text to the chart. The text includes specific mention of maximum and minimum values as well as context for understanding the information's distribution.

I sought more feedback by asking for three friends to criticize the chart on Facebook, sharing it using Gist and Bl.Ocks.org. I shared my third version with explanatory text. The following feedback is copied from our conversations and are formatted as responses to the following five questions -

What do you notice in the visualization?
What questions do you have about the data?
What relationships do you notice?
What do you think is the main takeaway from this visualization?
Is there something you don’t understand in the graphic?


Feedback #1 - Alex (Web developer, mathematician) ---

1. It's a bell curve distribution around .25 for the most part with a tail or bumps at lower averages, presumably as a result of players who are highly specialized in areas besides batting.

2. What's the breakdown of each batting average bin by player position? It would be interesting to see e.g. where pitchers cluster. What are some other details about the represented dataset? Which players from what time period are represented? This would be good information to put in a title/subtitle, in addition to the descriptive paragraph that's already there.

3. The bell curve distribution of batting averages. Besides distribution, it's hard to find relationships in a simple histogram.

4. That batting averages are distributed around ~0.25, and even the best are only ~0.3.

5. I guess I don't quite understand how the graphic demonstrates the claim that the margin between great and mediocre is razor thin. What is considered a great vs mediocre batting average? I guess the bell curve is fairly narrow - the graphic or the text could do more to point this out.

Feedback #2 - Elizabeth (Writer) ---

1. the visualization reminds me of a bell curve.

2. The paragraph reads like gibberish to me since I find batting averages confusing as all hell.

3.the relationship seems to be that the data is correlating batting averages with number of players
or connecting them

4. that most players have a 0.25 batting average, and it's rare to go above or below that (more rare to go above)

5. I think the title for the y axis could be a little clearer. It might just be my silly brain, but I thought number of players at first meant number of players on the team, rather than number of players in the American League (but that could be because it's 4am and I could very well have misread your paragraphs)

Feedback #3 - Joshua (Actual baseball fan) ---

1. the graph is crazy high and requires me to scroll down to see the whole thing and with the monitor at my work (21") i cant see it all in a single image, its very blocky not a complaint just stating its blocky ( not modern?)

2. what years are the players from? do batting averages differ from year to year? what was the average players average vs the people listed. 

3. uhhh ther eis a lot of .250 hitters?  so 1-4 must be league average? 

4. hitting is hard and 1/4 is good enough 

5. how did rod carew get such a good average / is it the best ever?

After these feedbacks, I changed the design fairly radically to the two-axis bar/line graph now presented.

***
RESOURCES -----

Most of the information that I used to finish this plot came directly from advanced examples on the Dimple.js website. These resources are listed in the references file.