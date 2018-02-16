---

 title: Community Library
  header:
  teaser: "/assets/images/IMG_5513.jpg"

---

# A MVC App to Manage & Share Books 

For the last couple of weeks, I've been tackling all things related to building dynamic web pages. From SQL and SQLite, to Sinatra, Active Record, RESTful routes, hashing algorithms and the model-view-controller (MVC) framework. Building a user friendly, dynamic web app requires a solid working knowledge of a variety of concepts, and the ability to implement them to build out the necessary framework and functionality. 

Stepping back, the number of moving parts can be intimidating. I started by mapping out the details and worked backwards from the views I would like to include, to the controllers that would route to those views and the models that would hold my data. As I'm an avid reader, and fortunate to have many friends with a similar interest, I thought it would be personally useful to build a website to keep track of books in my collection. And to encourage community, I added a component that allows users to mark books as "available for borrowing" so other users can borrow a book (and return when they're finished). 

Once I mapped out the views, I had a concept for the data I needed to collect and store to power those views. And to give my project room to expand, I decided to collect and store some additional data (like email addresses for permissioning or approval). One of my goals is to always create things that have room to grow beyond their initial scope so I can add functionality as my knowledge base grows. 

With that in mind, I started small and built out my migrations and introductory views (index, signup, login, logout, etc.). Once I was confident the model relationships were working correctly based on test data persisted to the database, I introduced views and routes with increased functionality, to create, update, show, and delete objects as needed. [DB Browser for SQLite](http://sqlitebrowser.org/) and [tux](https://rubygems.org/gems/tux/versions/0.3.0) were immensely helpful in this phase - the former helped me locate database entries that were missing information or otherwise creating issues, and the latter allowed me to update those entries before I had built out views and controllers within my application that facilitated those changes. And observing the data points and inputs that did not play nicely with my program allowed me to adjust my program accordingly to exclude those altogether. 

After building out various routes and views to power the functionality I envisioned, I spent some time making my application more visually appealing. Which is another realm for continual expansion and growth. But beyond aesthetic improvement, I've outlined a few other items to tackle...

### Future functionality: 
1. Permissioning: When a user "borrows" an available book, I would like to trigger an email to the book's owner indicating who would like to borrow the book, and reminding them to bring it along next time they see that person.
2. Timestamps: Currently, users can see who borrowed their book. Building on that, I would like to add when the book was borrowed (and potentially a "due date" concept).
3. Search functionality: Users can search their own books by author, title, genre, etc. This requires new controller routes and views, but would otherwise be easy to implement. 

Please check out the community library on [GitHub](https://github.com/AutumnJ/AutumnJ-community-library). 

And spare a moment to admire my favorite coding cat: 

![alt text](/assets/images/IMG_5513.JPG "Meow!")