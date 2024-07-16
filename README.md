# ad_recomendation
Ad recomendation ML Model, using NLP, cosine similarity and pytorch.

So this project has the rawdat6aset which I collected from my site.
Anyways 

It starts with using all-MiniLM-L6-v2 Model to do the most processing of keywords matching to user activity.

1st Step: 
I took all the categories in a dictionary, and then I took the input of a new keyword that doesn't exist in any categories of the dataset. Then I used all-MiniLM-L6-v2 to make a vector space of the dictionary of category and match the new keyword to a category given in datset.
This happens by finding cosine similarity by `util.pytorch_cos_sim`. Similarity score is calculated of every keyword inside every category compared to the new input keyword. then whichever is the highest score that category is returned.

2nd Step
Taking that category, the program takes all the users that have clicked the ad of that category(filtered dataset) and takes the input keyword and starts calculating similarity with all keywords present in the new filtered dataset finds the highest ones and returns top5 of those.
