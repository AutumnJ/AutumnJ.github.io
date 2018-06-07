---

 title: Heroku Deployment

---

# Debugging Deployment Issues

Earlier this week, I built and deployed a [self-destructing message application](https://still-shore-38939.herokuapp.com/), a clone of [TMWSD](https://www.thismessagewillselfdestruct.com/). I built it in Rails, with a tiny bit of JavaScript to power a fun, copy to clipboard feature. Since I planned on deploying it via [Heroku](https://www.heroku.com/), I incorporated [PostgreSQL](https://www.postgresql.org/) from the beginning. That likely saved me a lot of trouble when it came to deployment. But I figured writing a how-to as reference for future deployments on Heroku would still be valuable. 

Heroku has several guides on deployment, including one on [deploying with Git](https://devcenter.heroku.com/articles/git), which I chose. My app was in a subfolder of my original repository, so I made sure to navigate into that subfolder and initialize a Git repository there. I also installed the Heroku command line tools with `brew install heroku/brew/heroku`.

Then, I used the `heroku create` CLI command to create a new repository on Heroku. (At this point, I also set up an account on Heroku, as I was prompted to enter my email and password to proceed via the command line). And then `git push heroku master` to push my code to the Heroku remote. Up until this point, things went fairly well. I was able to run `git remote -v` and confirm that Heroku was set up as a remote based on the output. And the build proceeded as expected, without any fatal errors, after the `git push` command. 

But my application still wasn't live. To debug, I checked out the activity logs available on the Heroku dashboard. These were enormously helpful in debugging, as they provide fairly decent [error codes](https://devcenter.heroku.com/articles/error-codes). I also jumped over to another [guide](https://devcenter.heroku.com/articles/getting-started-with-rails5) available on Heroku's site, which is specific to deploying a Rails 5.x application.

After reading about the error code, and looking through the Rails-specific guide, I realized my database needed additional work. Even thought I had specified `adapter: postgresql` for production in `config/database.yml` I still needed to migrate my production database by running `heroku run rake db:migrate`. Unfortunately, the migration failed with the message `'production' database is not configured`. First, I went back and reconfigured my `config/database.yml` so it looked more like the one presented in the Heroku Rails guide. Next, I attached my credentials to the application by using the `addons:attach` command presented [here](https://devcenter.heroku.com/articles/heroku-postgresql-credentials). To do this, I needed to find the database name, which you can snag with the command `heroku addons` or you can snag it from the Heroku dashboard. I also needed to input the Heroku generated application name, which I found on my dashboard. The final command looked like this: `heroku addons:attach heroku-database-name-here --credential default -a heroku-app-name-here`. 

According to the Heroku documentation, this accomplishes the following: 

> If no other Heroku Postgres exist as part of the application that the database is being attached to, the credential will be assigned to the `DATABASE_URL` config var. If `DATABASE_URL` already exists on the application, the credential will be attached to the application using the format `HEROKU_POSTGRESQL_[COLOR]_URL`. 

After this, I used the `heroku config` command in the CLI to see my application's [`config vars`](https://devcenter.heroku.com/articles/config-vars). Then, in my application's `config/database.yml` I added a line to associate the credentials with my application: `url: <%= ENV['HEROKU_POSTGRESQL_[COLOR]_URL'] %>.` I committed this update prior to `git push heroku master` and then successfully ran `heroku run rake db:migrate`. 

And then, I celebrated my success by sending self-destructing messages to all my friends! Including this one...she hasn't read it yet....

![alt text](/assets/images/IMG_0469.JPG "Meow!")
