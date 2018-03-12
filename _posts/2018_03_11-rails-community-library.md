---

 title: Community Library - Rails Remix

---

# A MVC RAILS App to Manage & Share Books 

This post is similar to my last, as my latest project was a remix of my Sinatra MVC app. For this project I rebuilt it in Rails and added some new functionality. 

Using Rails to rebuild my project simplified a lot of aspects. Specifically: 
- The routes are far cleaner
- The addition of [Devise](https://github.com/plataformatec/devise) & [Omniauth for GitHub](https://github.com/omniauth/omniauth-github) simplified the login/authentication process
- Rails form builders help streamline the views 
- Adding nested attribute acceptance to models cleans up the controllers significantly

The downside of using Rails was that I lost touch with some of the files and folders the [Rails generators](http://guides.rubyonrails.org/generators.html) created. At first, I avoided using any generators, but building a Rails project totally from scratch seemed silly - part of the attraction of Rails is the generator shortcuts it supplies! However, the time I saved by utilizing Rails generators was likely cancelled out by the time I spent cleaning up unnecessary files at the end. (If that sounds unattractive definitely do not use Rails scaffolding...)

In terms of new features, I actually tackled a couple I did not identify on my last future functionality list. I added commenting capabilities, allowing a user who borrows a book to leave a comment that is visible to the book's owner, to other users when they view the book prior to borrowing, and to the original user, even after the book is returned. I also added show functionalities for authors and genres so instances of both are displayed as clickable links throughout the site. The link brings a user to a page that displays other books in their collection that match that genre or author, as clickable links.

### Future functionality: 
*The future functionality included in my last post is still in the works*
1. Permissioning: When a user "borrows" an available book, the book's owner sees a notification that the book has been borrowed and can update the status to reflect that the book has actually been lent out. And when the book is "returned" the owner can again update the status to show that they have the book back in hand.
2. Timestamps: Currently, users can see who borrowed their book. Building on that, I would like to add when the book was borrowed (and potentially a "due date" concept).
3. Search functionality: Users can search their own books by author, title, genre, etc.

Please check out the community library on [GitHub](https://github.com/AutumnJ/AutumnJ-community-library-rails). 

And check out this short walkthrough:

<iframe width="560" height="315" src="https://www.youtube.com/embed/tY9wlJQEd4w" frameborder="0" allowfullscreen></iframe>