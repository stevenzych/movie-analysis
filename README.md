# *Movie Analysis For Microsoft*
**Caleb Elgut and Steven Zych - June 2020**

# Introduction

For this research project, our team was tasked with aiding Microsoft's new movie studio in deciding what type of movies to make. We decided on four key questions designed to elucidate current trends in the film indFustry:
1. Is there a genre with low market share and high ROI that we can tap into?
1. How does a film's runtime affect its ROI?
1. Can the success of a non-English language film predict its ROI?
1. How does the length of a film's title affect its ratings?

We were given a set of data pulled from IMDB, Box Office Mojo, Rotten Tomatoes, The Movie Database, and The Numbers, which we then worked into operable Pandas DataFrames and SQL databases in order to answer our questions. All in all, the following packages were used:
- Pandas
- NumPy
- Seaborn
- Matplotlib
- SQLite3
- Glob

# Question 1: Underused Genres and ROI

We began our analysis with the assumption that Microsoft will want to distinguish itself from the many existing studios that already put out a great deal of content. We also assumed that while Microsoft will be willing to take risks, they will also want to ensure that their investors are kept safe. While this may not be Microsoft's primary stream of revenue, we imagine it will take a sizable investment to properly compete with Disney, Netflix, Amazon, and the like. These companies already have studios up and running. Therefore, we feel that genres with a low market share that return a high ROI could be the right place to begin. Finally, we start with an assumption that Horror will be among the genres with low prevalence and high ROI. With films like The Conjuring, Hereditary, and Midsommar becoming quite popular as of late and yet not so prevalent, this may be a genre in which Microsoft will want to invest.

Our first plot shows the distribution of ROI amongst the genres that hold between 2 and 6% of the market share. The two tables that we joined for analysis came from IMDB's title_basics data frame and The Movie Database's budgets database. After analyzing this plot, we realize that there are three genres worth examining more deeply: Adventure, Fantasy, and Animation. Unfortunately, even though Horror had the largest market share of the genres we analyzed and its distribution skews positively towards a higher ROI, we feel that the median ROI and symmetrical distribution may produce a more predictable result for the investors. 

![Boxplot of Low Market Share Genres and ROI](/readme_images/genre_roi_big.png)

Looking more closely at our three genres, we see that the median ROI for adventure and fantasy is 100, and for animation, it is 200. We can recommend that Microsoft look into a major animated film as one of its first releases as well as further research into whether or not it may be wise to combine the animation genre with adventure and fantasy.

![Boxplot of 3 Most Successful Low Market Share Genres ](/readme_images/genre_roi_over_100.png)

# Question 2: Runtime And ROI

For our next question, we tried to see if there was any relationship between a films runtime (in minutes) and its ROI. We assumed that this would at least have an impact on the edges of the runtime spectrum--We assumed that exceptionally short and exceptionally long films wouldn't do as well. Ultimately, this was not the case, as the following data show.

This first plot shows the general shape of our data. Here, runtime and worldwide ROI are seen to cluster around 100 minutes and a 100% return on investment (indicated by the blue median lines). However, our eye is drawn to these outlier dots flying high above the rest, with ludricous returns of 1000-4000%. We'll also notice that many of these "breakaway" successes cluster in a similar runtime range--about 75-120 minutes.

![Scatter Plot Of Runtime And ROI](/readme_images/runtime_scatter.PNG)

So, does this mean this runtime range is the sweet spot for Microsoft to make movies in? Perhaps not. As the following plot of runtime and median ROI shows, a sizeable piece of this range (seen below in the 60-89 minute bin) tends towards **losing** money. However, the other portion of this range (seen below in the 90-119 bin) tends towards **earning** money, *and* contains a fair number of breakaway successes. As such, we recommend that Microsoft's new studios aim to make films that sit comfortably within this 90-119 minutes range. 

![Bar Plot Of Runtime And Median ROI](/readme_images/runtime_bar.PNG)

# Question 3: Language and ROI

Our third question brought us to a topic that many studios seem to be looking at more and more recently. As Netflix continues to extend its reach around the world creating such successful non-English-speaking shows as Fauda (Hebrew), Caliphate (Swedish), and Kingdoms (South Korean) as well as films such as the incredibly-successful Jak zostałem gangsterem. Historia prawdziwa (Polish), languages is not a category that we believe Microsoft should ignore. While the studio may not need to consider this at the beginning of its launch, it may be wise to eventually consider investing in films translated into and perhaps even filmed originally in languages aside from English. We assume that there is a market for non-English-speaking films that will turn into a healthy ROI for investors. 

Our plot below reflects encouraging results for our assumption! After separating our languages and plotting them against their corresponding ROI, we determined that the top four non-English languages (representing between 4 and 20% of the market share) were Hebrew, Turkish, French, and Swedish. Hebrew and Turkish returned an ROI of around 200; however, neither of the other two languages dipped below a 150 ROI. This finding leads us to believe that it is money well spent to invest in a dubbing department and, perhaps, invest in productions that will be filmed in one of the four languages we have mentioned, particularly Hebrew or Turkish. 

![Boxplot of Non-English Language Films and ROI](/readme_images/roi_of_language.png)

# Question 4: Title Length And Ratings

Our final research question investigated something a little stranger: Was their any correlation between a film's title length (counted in words, not letters) and how well it was rated? We intially assumed that there would be a correlation, that longer-named films would do worse than their shorter-named counterparts. After all, many movies have *you* seen with a twelve-word title? At the very least, lengthy names sounded like a left-field move.

However, the data proved us wrong and showed that actually there is nearly no correlation between a film's title length and its average ratings. The plot below groups all films with the same title length and takes the overall average score. Note that group 16 is not an error, it just only contains one film.

![Violin Plot Of Title Length And Average Rating](/readme_images/titlelength_violin.PNG)

It's almost a strangely consistent plot. To see if there was anything else going on, we took a look at the **total amount of ratings** given for all films with the same title length. Looking from group 2 to group 16, we see an almost perfect model of exponential decay. As title lengths go up, total number of reviews go down. But, let us not forget that the **total number of films** is also going down as title lengths go up.

![Line Plot Of Title Length And Total Ratings For All Films Of Same Length](/readme_images/titlelength_line.PNG)

For this question's final plot, we looked at a more relative metric, **average number of ratings for any film with a given title length.** In other words, this plot shows how many ratings an x-word-title film is expected to get, and it's *quite* different from the previous plots. Whereas the last two were exceptionally regular, this one is nearly categorical. Films with one-to-seven word titles get around 9000 ratings, films with eight word titles get around **fifteen-thousand** ratings, and films with nine-or-more word titles dwindle off to nearly nothing.

![Bar Plot Of Average Number Of Ratings For Films With A Given Title Length](/readme_images/titlelength_bar.PNG)

Further research is needed to sus out *why* this is going on, but for the time being we can say this: If Microsoft cares about how many ratings they're getting on IMDB and similar websites, we encourage them to give their films eight (or less) word titles.

# Recommendations

In order for Microsoft to be successful in their cinematic ventures, it is imperative they follow the recommendations towards which this research builds. Here, below, they are listed in their simplest forms:
1. Make sure an animated film is one of the first films you release!
1. Movies should be 90-119 minutes long.
1. Hebrew & Turkish should be considered as languages for future projects. 
1. Movie titles should be 8 words or less.

# Future Research

Of course, no set of research is perfect, and no set of research wouldn't be enhance with more time or better resources. For each question below we have listed what would improve the accuracy and significance of our findings:
1. Genre and ROI: It will be worth examining whether or not we can combine animation, adventure, and fantasy together to bring in an even greater ROI than what they already bring on their own. 
1. Runtime And ROI: If we had the time to focus on only movies made by major studios, we may have seen different distributions of median ROI. It is possible that many indie films are in the range with a negative median ROI.
1. Language And ROI: It is possible that the ROI for the languages we looked at will be higher if they are in films created in the region and/or nation that the language is primarily spoken in. It would be worth looking into, for example, whether a Turkish-language film produced in America would receive the same ROI as one produced in Turkey. 
1. Title Length And Rating: If we had the time and data to explore this question in regards to film translations as well, we could provide Microsoft with better insight into how to name their films when releasing globally.

# Conclusion

**Conclude, thank Microsoft, etc.**
