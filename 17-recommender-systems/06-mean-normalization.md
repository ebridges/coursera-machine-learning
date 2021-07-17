---
Video: machine-learning/16_recommender-systems/03_low-rank-matrix-factorization/02_implementational-detail-mean-normalization.mp4
---

### Mean Normalization

Take into consideration the case where we have a user who has not rated any movies.  The  parameters $\theta$ will end up being a matrix of zeroes as this user has not rated anything for us to associate any features with. Because they will not have any movies to suggest, then we won't also have any to recommend as well.

Using mean normalization can help with this problem. 

Let us group all movie ratings into matrix $Y$ , note last column represents a new user:
$$
Y=\begin{bmatrix}5&5&0&0&?\\ 5&?&?&0&?\\ ?&4&0&?&?\\ 0&0&5&4&?\\ 0&0&5&0&?\end{bmatrix}
$$
To implement mean normalization, first compute the mean rating of each movie:
$$
\mu = \begin{bmatrix} 2.5 \\ 2.5 \\ 2 \\ 2.25 \\ 1.25 \end{bmatrix}
$$
Now, look at all movie ratings and subtract the mean for each movie from each average rating for that movie, thus normalizing all ratings to have an average rating of zero:
$$
Y_{\mu}=\begin{bmatrix}2.5&2.5&-2.5&-2.5&?\\ 2.5&?&?&-2.5&?\\ ?&2&-2&?&?\\ -2.25&-2.25&2.75&1.75&?\\ -1.25&-1.25&3.75&-1.25&?\end{bmatrix}
$$
Next we take this set of ratings and use that as the dataset to learn $\theta{(j)}$ and $x^{(i)}$.

When I want to make predictions, for user $j$ on movie $i$ predict:
$$
(\theta^{(j)})(x^{(i)})+\mu_i
$$
Where $\theta^{(j)}$ and $x^{(i)}$ are the parameters we've learned from the mean normalized dataset.  But, because we've subracted out the means to normalize the dataset, we'd add back that adjusting factor.

So, in effect, for a new user we will be predicting the average rating for what each movie received.

