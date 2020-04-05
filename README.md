# Movie-Recommendation

## What are recommender systems? 

Well, like I said Amazon is a great example, and one I'm very familiar with. So, if you go to their recommendations section, you can see that it will recommend things that you might be interested in purchasing based on your past behavior on the site. The recommender system might include things that you've rated, or things that you bought, and other data as well. But, it's pretty cool. You can also think of the people who bought this also bought feature on Amazon as a form of recommender system.

## User-based collaborative filtering 
First, let's talk about recommending stuff based on your past behavior. One technique is called user-based collaborative filtering, and here's how it works: 

*Collaborative filtering, by the way, is just a fancy name for saying recommending stuff based on the combination of what you did and what everybody else did, okay? So, it's looking at your behavior and comparing that to everyone else's behavior, to arrive at the things that might be interesting to you that you haven't heard of yet.*

1. The idea here is we build up a matrix of everything that every user has ever bought, or viewed, or rated, or whatever signal of interest that you want to base the system on. So basically, we end up with a row for every user in our system, and that row contains all the things they did that might indicate some sort of interest in a given product. So, picture a table, I have users for the rows, and each column is an item, okay? That might be a movie, a product, a web page, whatever; you can use this for many different things.
2. I then use that matrix to compute the similarity between different users. So, I basically treat each row of this as a vector and I can compute the similarity between each vector of users, based on their behavior. 
3. Two users who liked mostly the same things would be very similar to each other and I can then sort this by those similarity scores. If I can find all the users similar to you based on their past behavior, I can then find the users most similar to me, and recommend stuff that they liked that I didn't look at yet.

## Limitations of user-based collaborative filtering 

Now, unfortunately, user-based collaborative filtering has some limitations. When we think about relationships and recommending things based on relationships between items and people and whatnot, our mind tends to go on relationships between people. So, we want to find people that are similar to you and recommend stuff that they liked. That's kind of the intuitive thing to do, but it's not the best thing to do! The following is the list of some limitations of user-based collaborative filtering: 

1. One problem is that people are fickle; their tastes are always changing. So, maybe that nice lady in the previous example had sort of a brief science fiction action film phase that she went through and then she got over it, and maybe later in her life she started getting more into dramas or romance films or romcoms. So, what would happen if my Edgy Mohawk guy ended up with a high similarity to her just based on her earlier sci-fi period, and we ended up recommending romantic comedies to him as a result? That would be bad. I mean, there is some protection against that in terms of how we compute the similarity scores to begin with, but it still pollutes our data that people's tastes can change over time. So, comparing people to people isn't always a straightforward thing to do, because people change.

2. The other problem is that there's usually a lot more people than there are things in your system, so 7 billion people in the world and counting, there's probably not 7 billion movies in the world, or 7 billion items that you might be recommending out of your catalog. The computational problem finding all the similarities between all of the users in your system is probably much greater than the problem of finding similarities between the items in your system. So, by focusing the system on users, you're making your computational problem a lot harder than it might need to be, because you have a lot of users, at least hopefully you do if you're working for a successful company. 

3. The final problem is that people do bad things. There's a very real economic incentive to make sure that your product or your movie or whatever it is gets recommended to people, and there are people who try to game the system to make that happen for their new movie, or their new product, or their new book, or whatever.

*It's pretty easy to fabricate fake personas in the system by creating a new user and having them do a sequence of events that likes a lot of popular items and then likes your item too. This is called a shilling attack, and we want to ideally have a system that can deal with that.*

There is research around how to detect and avoid these shilling attacks in user-based collaborative filtering, but an even better approach would be to use a totally different approach entirely that's not so susceptible to gaming the system.   

That's user-based collaborative filtering. Again, it's a simple concept-you look at similarities between users based on their behavior, and recommend stuff that a user enjoyed that was similar to you, that you haven't seen yet. Now, that does have its limitations as we talked about. So, let's talk about flipping the whole thing on its head, with a technique called item-based collaborative filtering.
