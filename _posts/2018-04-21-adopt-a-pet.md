---

 title: Adopt-a-Pet

---

# Gamified Adoptable Pet Browser

My initial idea for my final project was to expand upon my first, and incorporate my [pets-seeking-people scraper gem](https://github.com/AutumnJ/AutumnJ-cli-app) into an online pet browser. But, in the interest of keeping things scalable, I wanted to find a more reliable source of data, so I chose the [Petfinder API](https://www.petfinder.com/developers/api-docs) from this [fabulous list of public APIs](https://github.com/toddmotto/public-apis). I am looking forward to using the [HTTP cats API](https://http.cat/) on a future project! 

![alt text](/assets/images/100Error.png "Continue")

The Petfinder API documentation is fairly straightforward, so after a few test runs in [Postman](https://www.getpostman.com/) I was ready to drop it into my application's fetch requests. After fetching from Petfinder, I formatted and persisted the returned data to my internal Rails API. Unfortunately, I set up my database with SQLite, which had issues handling the volume and frequency of the data persistence. After moving to PostgreSQL and setting up pgAdmin to keep an eye on my database, I was fetching and persisting data with ease. 

The next challenge was incorporating Redux's state management on the front end. The React and Redux dev tools were enormously helpful in tracking state flow, as were [articles](https://medium.com/codingthesmartway-com-blog/learn-redux-introduction-to-state-management-with-react-b87bc570b12a) on best practices and [patterns](https://github.com/chantastic/reactpatterns.com#function-as-children). After I created the first iteration of my actions and reducers, I moved on to the architecture of the React components and containers. In this arena I was more flexible with the design. As my application grew, and I passed state and props from parent to child, I started shifting more and more elements from containers to components.

My first React container/component implementation was a pretty brute force solution. Once things were working, I found almost endless areas to improve upon, and spent a significant amount of time refactoring for readability and brevity, making my components usable by more container elements, and adding some [style](https://react-bootstrap.github.io/)!

And on that note, I'm off to refactor some more! Check out the latest iteration of Adopt-a-Pet on [GitHub](https://github.com/AutumnJ/adopt-a-pet-game). And/or take a peek at the adorable animals up for adoption in my walkthrough!

<iframe width="560" height="315" src="https://www.youtube.com/embed/rumehkzhJaY" frameborder="0" allowfullscreen></iframe>
<br/>

While I've been working, my own adopted kitty is getting ready for a summer on the patio:

![alt text](/assets/images/IMG_6060.JPG "Meow!")