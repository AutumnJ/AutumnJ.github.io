---

 title: Community Library - jQuery + Rails
 header:
  teaser: "/assets/images/IMG_5964.JPG"

---

# Adding AJAX to an Existing Application

With my existing Community Library functioning well in Rails, it was challenging to determine how to incorporate jQuery. Should I refactor existing components? Add functionality? Extend existing functionality? 

At some point, I would like all of my projects to be used by actual people. With that end user in mind, I identified weaknesses in my existing application, which could be resolved with the addition of jQuery, and identified a few components that would be nice to have, which could be easily added with jQuery.

For the former, I redid the new comment feature. Instead of being taken to a new page to add a comment, the form is located on the current page and the new comment is rendered without refresh upon submission. 

For the latter, I added a custom pagination to the comments show view, allowing a user to easily page through their comments and edit as needed. This component was trickier to implement than it seemed on the surface. As each comment is associated with a specific book, the route for a comment appears as: 

### /book/:book_id/comments/:id 

Had it not been a nested resource, and if I had wanted to allow users to page through *all* comments vs. *their* comments it would have been simple to increment a data-id attribute on the show page and make a GET request accordingly. Since that approach would not work for this use case, I configured my GET request to pull in the user's collection of comments (vs. one comment). I set a custom counter based on where they begin paging through in the collection (i.e. comment 3 of 8) and incremented a data-id attribute on the page accordingly. 

But possibly my favorite feature is the new search page! An application's ease of use is hugely important to the user experience. And being able to quickly search one's collection for a book is hugely useful!

Even with all these great additions, I'm still preoccupied with what's next. Which is arguably one of the best parts of programming - the ever-present room for innovation and improvement!

Check out this short walkthrough:

<iframe width="560" height="315" src="https://www.youtube.com/embed/l9JH1q5DDcI" frameborder="0" allowfullscreen></iframe>

If you need a break from code, consider perusing pets available for adoption using [pets_seeking_people](https://autumnj.github.io//ruby-gem/):

![alt text](/assets/images/IMG_5964.JPG "Meow!")