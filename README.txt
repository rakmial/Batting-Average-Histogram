***
SUMMARY-----

This interactive histogram demonstrates the distribution of batting averages across a dataset of 1,157 baseball players, displaying only those players with an average greater than zero. A baseball player's batting average is the ratio of pitches hit against total pitches thrown to them, naturally resulting in a ratio from 0 (has never hit any pitch thrown) to 1 (hits every pitch thrown). The histogram exposes the number of players that fall into each bin of width .005. Mousing over bins activates a tooltip listing the names and batting averages of players contained within the bin.

***
DESIGN -----

The first important design decision to be made involved players with a 0.000 batting average. Nearly 23% of observations had this value. When I first made my histogram, the 0.00 batting average observations ruined the scale of the chart - the y-axis must be stretched greatly to show the bin of magnitude 266, and entirety of non-zero observations fit into a domain between 0.066 and 0.328, leaving a great white gap between 0.000 and 0.066.

It was possible to design the story around this feature of the data - the fact that more than a fifth of the players in the dataset had never hit a single pitch is interesting, but it wasn't a story I was interested in telling. Using R to subset the data, I removed observations of players with a batting average of 0.000.

The next design decision came with the scale of the axes. The y-axis required some decision on whether to use a linear or log scale D3 object - the data is so centralized that a logarithmic scale might seem necessary. The x-axis required a decision with regard to empty space - technically, the x-axis could extend to 1.0 even though the highest observation was 0.328.

I chose to keep the scale linear but curtail the x-axis to 0.35. I found this gave the most intuitive shaping of the histogram to the data - highly normal with a gentle left skew.

I found that this shape of the chart naturally leads to exploration of the extremes - the smallest and greatest values, both of batting average and number of players. Dean Chance and Rod Carew are, in a sense, the stars of this story, having the maximum and minimum batting averages, but the wall of players with averages between 0.250 and 0.255 form another narrative character in the chart - the fulcrum.

***
FEEDBACK -----

My next changes were made after receiving feedback from roommates. They noted that my original settings for the font in the tooltips made it hard to read, and player names and values for the tallest bins sometimes clipped out of the window. I altered settings to shrink the font and margins, grouping the names more tightly. However, this made the names harder to read. Eventually I settled on a small-caps lettering theme that made the smaller font/margin readable even when compressed closely. I changed my x- and y-axis labels to match the tooltip as well.

I was pleased that my roommates had a similar experience with the chart as I did, wondering aloud who Dean Chance and Rod Carew were. Luckily, I had already read their wikis and could tell them. However, that kind of narrative guiding would work well paired with an article about batting averages, particularly if they specifically mentioned Chance and Carew.

***
RESOURCES -----

I must first and foremost acknowledge the guidance I found in Frank Cleary's personal website. I knew the type of chart I wanted to create, but I wasn't yet sure how I wanted to make it interactive. His histogram tracking the distribution of average MPG for his Prius formed much of the heart of my own chart as well as the inspiration to use the tooltip package. A few of his works may be found at:

http://www.frankcleary.com/mpg/ 

I used a number of resources for this project - they are listed in a separate references file.