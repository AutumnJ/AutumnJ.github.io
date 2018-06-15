---

 title: Rails Improved

---

# Revisiting Rails 

While my last post covered the deployment process for my [self-destructing message application](https://still-shore-38939.herokuapp.com/), this one is focused more on, 1) what I did differently in building this project, in light of my growing knowledge, 2) what I *will* do differently in the future (and will go back and refactor in this project), given recent feedback. 

In regards to what I approached differently, based on what I've learned from *previous* projects:

1. I chose a database that fit my needs and end goal, rather than simply choosing one I was familiar with. This is something I've been cognizant of as my skills have grown. While it was acceptable to go with what I knew for a certain amount of time, I have now reached the stage where decisions about what I do and do not incorporate in projects *should* be more strategic. 

2. Be consistent in making small changes and testing as they are implemented, or writing tests and implementing code to pass those tests in a consistent, gradual manner. In the past, in my excitement around implementing a feature or refactoring existing code, I have made too many changes in too many different realms of Rails' MVC framework, which can make debugging issues more time-consuming. Testing should be continual as changes are implemented. 

3. I incorporated gems I intended to use, and removed or commented out gems I was no longer using. This made my Gemfile far more readable, and could prevent me from encountering future gem dependency issues with gems I wasn't even using.

4. Keep the routes clean. It's easy to use `resources` to quickly define CRUD routes for a controller. But if all the routes aren't being used, it could be misleading when someone else takes a peek at your code, or when you glance back at it in a year's time. It's always best to be as concise as possible for added clarity. 

As for what I *will* do differently next time: 

1. Keep a better eye on the separation of concerns. I was initially proud of the brevity of my controller actions. But, despite their brevity, a couple contained snippets that could be refactored or relocated to provide a better separation of concerns.

2. Avoid using `require ...` in the controller(s) to include gems unnecessarily. If a gem does need to be included using `require`, add that to the `ApplicationController` so the other controllers can easily utilize the gem without its explicit inclusion in each controller. 

3. Incorporate custom actions into their own controllers as much as possible. I had two actions related to password verification for my messaging application. I created custom actions on my `MessagesController` to accommodate those, but really should have separated them into their own controller and used a standard CRUD route for the two actions I defined. 

Ultimately, the project provided me with a great opportunity to appreciate what I've learned. It's exciting to reach a stage where I am able to iteratively identify better ways to accomplish things. And it also gave me a great opportunity to absorb fabulous feedback from people far more seasoned than myself, thus empowering the next iteration of creating a better Rails application!




