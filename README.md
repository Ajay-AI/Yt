# Yt
The idea was to make recommendation for required topics better than the YouTube recommendation. So to achieve this I started collecting different search results by using search().list() and using that data I retrieved the statistics(View Count, Like Count, Dislike Count, Favourite Count), Duration and Published At for the corresponding search results by passing the Video ID as argument to videos().list().
## Approach
- The Approach for recommendation Technique was to implement a scoring function which gives scores based on the Duration of the Video, Like Count, View Count and Dislike Count of the video.
- Z-Score normalisation was used to normalize Duration, ViewCount, LikeCount, DislikeCount Columns.
- Scoring Function was created by giving weights to Duration_zscore, Views_zscore, Likes_zscore, Dislikes_zscore.
- Videos with very long duration tend to have lesser views compared to those with smaller duration which gives those videos a disadvantage so to even this out Duration was also given significant weight in the scoring function. 
- Also, Dislike Count was given negative weight to make sure that only the best videos come at top during ranking of the videos based on score value.
## APIs Used:
- Search: list
- Videos: list
## Filters Used:
- The Videos which were longer than a minute (60 seconds) was chosen for analysis.
## Challenges Faced:
- Main challenge was to get more rows of data while Search: list API has limit of 500 results.
- In some of the data the Like Count and Dislike Count was not available, so it led to removal of those data has they will affect the scoring function badly.
- In some cases, the search results contained YouTube Ads related to the topic itself, which are generally of 10-20 seconds. Those videos have enormous views and affected the analysis so these short videos were removed.
## Key Learnings from Data Analysis:
- It was observed that most (almost 80%) of the videos were having less than 1 lakh views while some were having millions of views.
- Among my three topics (Data Structures, Fluid Mechanics and Data Science) I observed that Data Science was most viewed topic while Fluid Mechanics was the least viewed in YouTube.
## References:
- https://matplotlib.org/tutorials/introductory/pyplot.html
- https://pandas.pydata.org/pandas-docs/stable/user_guide/merging.html

