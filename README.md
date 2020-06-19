# *Movie Analysis For Microsoft*
**Caleb Elgut and Steven Zych - June 2020**

# Introduction

For this research project, our team was tasked with aiding Microsoft's new movie studio in deciding what type of movies to make. We decided on four key questions designed to elucidate current trends in the film industry:
1. **CALEB QUESTION 1**
1. How does a film's runtime affect its ROI?
1. **CALEB QUESTION 2**
1. How does the length of a film's title affect its ratings?

We were given a set of data pulled from IMDB, Box Office Mojo, Rotten Tomatoes, The Movie Database, and The Numbers, which we then worked into operable Pandas DataFrames and SQL databases in order to answer our questions. All in all, the following packages were used:
`* pandas
* numpy`
`* seaborn
* matplotlib`
`*sqlite3
* glob`

# Question 1: 

**CALEB QUESTION 1. Remember for each Q Abhineet said we should have:assumption, finding, reccomendation**

# Question 2: Runtime And ROI

For our next question, we tried to see if there was any relationship between a films runtime (in minutes) and its ROI. We assumed that this would at least have an impact on the edges of the runtime spectrum--We assumed that exceptionally short and exceptionally long films wouldn't do as well. Ultimately, this was not the case, as the following data show.

This first plot shows the general shape of our data. Here, runtime and worldwide ROI are seen to cluster around 100 minutes and a 100% return on investment (indicated by the blue median lines). However, our eye is drawn to these outlier dots flying high above the rest, with ludricous returns of 1000-4000%. We'll also notice that many of these "breakaway" successes cluster in a similar runtime range--about 75-120 minutes.

![Scatter Plot Of Runtime And ROI](/readme_images/runtime_scatter.PNG)

So, does this mean this runtime range is the sweet spot for Microsoft to make movies in? Perhaps not. As the following plot of runtime and median ROI shows, a sizeable piece of this range (seen below in the 60-89 minute bin) tends towards **losing** money. However, the other portion of this range (seen below in the 90-119 bin) tends towards **earning** money, *and* contains a fair number of breakaway successes. As such, we recommend that Microsoft's new studios aim to make films that sit comfortably within this 90-119 minutes range. 

![Bar Plot Of Runtime And Median ROI](/readme_images/runtime_bar.PNG)

# Question 3:

**CALEB QUESTION 2. Remember for each Q Abhineet said we should have:assumption, finding, reccomendation**

# Question 4: Title Length And Ratings

![Violin Plot Of Title Length And Average Rating](/readme_images/titlelength_violin.PNG)
![Line Plot Of Title Length And Total Ratings For All Films Of Same Length](/readme_images/titlelength_line.PNG)
![Bar Plot Of Average Number Of Ratings For Films With A Given Title Length](/readme_images/titlelength_bar.PNG)

# Recommendations

In order for Microsoft to be successful in their cinematic ventures, it is imperative they follow the recommendations towards which this research builds. Here, below, they are listed in their simplest forms:
1. **CALEB**
1. Movies should be 90-119 minutes long.
1. **CALEB**
1. Movie titles should be 8 words or less.

# Future Research

Of course, no set of research is perfect, and no set of research wouldn't be enhance with more time or better resources. For each question below we have listed what would improve the accuracy and significance of our findings:
1. **CALEB**
1. 
1. **CALEB**
1. 

# Conclusion

**Conclude, thank Microsoft, etc.**