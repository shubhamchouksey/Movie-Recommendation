# Movie-Recommendation

## What are recommender systems? 

Well, like I said Amazon is a great example, and one I'm very familiar with. So, if you go to their recommendations section, you can see that it will recommend things that you might be interested in purchasing based on your past behavior on the site. The recommender system might include things that you've rated, or things that you bought, and other data as well. But, it's pretty cool. You can also think of the people who bought this also bought feature on Amazon as a form of recommender system.

## User-based collaborative filtering 
First, let's talk about recommending stuff based on your past behavior. One technique is called user-based collaborative filtering, and here's how it works: 

*Collaborative filtering, by the way, is just a fancy name for saying recommending stuff based on the combination of what you did and what everybody else did, okay? So, it's looking at your behavior and comparing that to everyone else's behavior, to arrive at the things that might be interesting to you that you haven't heard of yet.*

1. The idea here is we build up a matrix of everything that every user has ever bought, or viewed, or rated, or whatever signal of interest that you want to base the system on. So basically, we end up with a row for every user in our system, and that row contains all the things they did that might indicate some sort of interest in a given product. So, picture a table, I have users for the rows, and each column is an item, okay? That might be a movie, a product, a web page, whatever; you can use this for many different things.
2. I then use that matrix to compute the similarity between different users. So, I basically treat each row of this as a vector and I can compute the similarity between each vector of users, based on their behavior. 
3. Two users who liked mostly the same things would be very similar to each other and I can then sort this by those similarity scores. If I can find all the users similar to you based on their past behavior, I can then find the users most similar to me, and recommend stuff that they liked that I didn't look at yet.
