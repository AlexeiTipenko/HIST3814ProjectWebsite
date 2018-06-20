# Insights and Visualizations

After I ended up with a clean csv file containing all the various events and their corresponding dates, I began to create various visualizations to understand what all the data means.

The first aspect of the data I turned to was the dates. I used RStudio, along with the ggplot2, scales and lubridate packages to create a histogram for both the documented dates and the event dates.

Here is the graph for the event dates:

![Histogram file](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/visualizations/Event_Date_Histogram.png?raw=true)

Here is the graph for the documented dates:

![Histogram file](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/visualizations/Doc_Date_Histogram.png?raw=true)

The first histogram contains some outliers, however the two graphs seem to follow an almost identical pattern. The only exception is the unusual rise in documented event dates in the summer months of 1918. What this says about the diaries is that most documented dates were reported at nearly the same time as the actual events. This means that the hospital was quite meticulous when it came to their documentation.

We can also see that there is spike in events at the start of 1918 and another one between September and October of the same year. This means that the hospital had greater activity at these times, which could imply an increase in combatant casualties. From these histograms alone, you can infer the activity of Canada's military in the First World War. Since the war started in 1914, perhaps Canada wasn't all that active at its beginning and made significantly greater contributions during the last year of the war. However, this isn't necessarily the case. Perhaps the hospital was only operational in the last 1 or 2 years of the war, or there are parts of the diaries that were simply not recovered. It's important to take the insights from these histograms with a grain of salt, but they do show an interesting pattern that could gain more validity when combined with more data from this time period.

The other aspect of the data that is quite important is the event description. The main tool I used to analyze this data was [voyant tools](http://voyant-tools.org/). This tool is very powerful and has generated several visualizations that can be useful. I began by looking at the individual words within the data. After transcribing a portion of the documents myself and working with them closely, what I discovered from voyant was no surprise.

Here are the most common words used in the event descriptions:

![Cirrus](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/visualizations/word_cirrus.png?raw=true)

A large amount of events documented in the diaries were simply "X taken on strength" or "Y struck off the strength". So the most common words would have to be strength, struck, taken, etc. The diaries also frequently mentioned the C.A.M.C Depot. Several other similar events indicate that it is a "reserve and training depot". In other words, this is a location where soldiers are strategically placed for future military action. This particular depot was also a military site where some training took place as well. There are also other common words included in the above visualization. These words are common in the military vocabulary, such as nursing (sister), ranks, casualty, captain, regimental and attached.

So how do these common words interact with each other over time? Here's another visualization:

![Line graph](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/visualizations/word_trends.png?raw=true)

C.A.M.C., depot, strength and struck all follow the same sort of pattern. All 4 loosely follow the same fluctuations. The interesting this is the dip in relative frequency for the 4 words. This implies that an event like "X struck off the strength from c.a.m.c. depot" was used more often near the end of the war. In a casualty form, taken or being struck off strength refers to [military personnel movement](https://www.bac-lac.gc.ca/eng/discover/military-heritage/first-world-war/Pages/read-service-record-casualty-form.aspx) within a unit. So taking on strength means entering a certain unit and being struck off strength means leaving a unit. The dip in the visualization could mean that the military units in the C.A.M.C. depot were mobilized for military action and sent off. This implies that less military personnel would be leaving their unit because they would be occupied on the battlegrounds. Another interesting thing about this visualization is how the frequency of the word "taken" doesn't seem to change that much. This word frequency by itself could indicate the relative stream of new recruits joining new units. There are multiple combinations of graphs and visualizations that can be built directly with voyant. Feel free to play around with more of my visualizations by heading to this [link](http://voyant-tools.org/?corpus=99dfaee28e430b5efe8b5105740bde23).

One final question I had regarding the data was how the different names mentioned in the event description section compared to one another. Here is another visualization of the most popular names in the diaries:

![Cirrus](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo/blob/master/visualizations/names_cirrus.png?raw=true)

It is clear from this visualization that the most common names in the event descriptions had the same relative frequency. C.A.Young has been mentioned 8 times and the next 3 common names are trailing close behind with 5 instances. This says something about the nature of the events in the diary. It is already established that many of the events have to do with the movement of military personnel. So it makes sense for names to only show up a few times. A normal troop would probably be taking on strength for a unit, then leaving it for another unit a year or two later. It wouldn't make sense to constantly move personnel around. It could be the case that the most common names were mistakenly transferred between units a few too many times. Or maybe these people had importance in relation to the hospital and the depot. If you are interested in exploring name specific data through various visualizations, you can find that [here](http://voyant-tools.org/?corpus=435d9253e10c4fc58957110a9e16fa3c).

These visualizations have provided some interesting insights on the 14th General Hospital and the potential state of the Canadian military during World War One. Before starting this project, I assumed that the majority of the insights would involve the hospital directly. I was quite surprised to find out that even basic information like military personnel movement can produce insights on the state of the Canadian military at a given time and important dates during the war itself.

If you would like to see any of the files for this project, please visit the project repository my GitHub [page](https://github.com/AlexeiTipenko/HIST3814O_Project_Repo).
