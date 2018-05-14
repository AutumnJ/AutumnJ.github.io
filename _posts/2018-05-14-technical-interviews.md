---

 title: Tackling Technical Interview Problems
 header:
  teaser: "/assets/images/IMG_6234.JPG"

---

# Matrix Spiral Copy: Plan of Attack

In preparation for a successful job hunt, I've been tackling practice technical interviews and brushing up on algorithm challenges. [Pramp](https://www.pramp.com/) is a great resource for practicing technical problems in an interview setting, as it allows you to be the interviewer for half the session (30 minutes) and the interviewee for the other half. Taking on the role of interviewer, and coaching and guiding the interviewee certainly helped deepen my conceptual understanding (and I'm far more sympathetic to interviewers now)! 

During my first Pramp interview, I received a [spiral matrix problem](https://www.geeksforgeeks.org/print-a-given-matrix-in-spiral-form/) that I'd *seen* before, but hadn't yet solved. Fortunately, my portfolio project reviews during Flatiron's program positioned me well to code a working solution on the spot. I also keep this [cracking the coding skills](http://www.crackingthecodinginterview.com/uploads/6/5/2/8/6528028/cracking_the_coding_skills_-_v6.pdf) breakdown by my desk, as I've found it immensely helpful. I adapt it a little depending on the time constraints. And in solving the spiral matrix problem, I implemented the following plan of attack: 

1. Read the instructions aloud or repeat verbal directions back to the interviewer. This allows time to: 1) process the problem, 2) identify any glaring errors in conceptual understanding. 

2. Ask clarifying questions. Generally, it's best to avoid asking questions like "Can I use JavaScript's built-in X method?" Stick with asking forgiveness over permission when it comes to utilizing built-in functionality. Instead, if you're conceptually unclear and the interviewer did not correct or clarify anything when you repeated the directions back, ask those niggling questions now.

3. Think through any edge cases. Pramp's platform is great in that it makes steps one and two very easy, which saves a decent chunk of time in a timed interview, so I moved to item three rather quickly. The most glaring edge cases for the spiral matrix problem involve the input size - if the input only includes one array, will the solution still work?

4. Write tests or run existing tests. Some advise running tests immediately after reading the problem. However, I think being able to articulate the edge cases prior to running tests displays a certain understanding that interviewers may appreciate. Pramp supplies tests for each problem, which saves time. In some platforms, the tests are visible, so you could just read them vs. running them. 

5. Pseudocode a plan of attack. If I don't code a working solution in the allotted time, I'd like the interviewer to know I understood the problem and *could* code a working solution given more time - writing pseudocode does just that. This also allows the interviewer the opportunity to intervene if you're on the wrong track (some may not, but hopefully they do). 

6. Identify a brute force solution. I started on my brute force solution 5-7 minutes into the 30-minute timeslot. To me, this step is still more pseudocode than code. I wrote a few lines of code that I *thought* would solve the smallest test case for the spiral matrix problem and ran the tests again to confirm, but my solution didn't work. Since my brute force solution simply wouldn't work, and certainly wouldn't scale, I backed out and identified another. 

7. Code a brute force solution. Once I identified a more viable brute force solution, I coded that version. While writing actual code, I try to be especially careful to avoid any simple typos. What may be a simple typo to me may signal to the interviewer that I lack a syntactical understanding of the language. 

8. Optimize the solution. As time allows, I verbalize my approach again, identifying areas that could be optimized. This includes areas that could be optimized for a better runtime, and also areas of code that seem non-standard or unusual. Articulating the runtime advantages of other solutions, even if you don't have time to implement them, (hopefully) displays a level of competency the interviewer will appreciate. 

9. If time remains, continue optimizing the solution. And/or add additional tests that may break your code. Breaking code to improve it is always a good thing!

I'll admit, I did not make it to item nine in my attempt to solve the spiral matrix problem. But my brute force solution was *almost* working by the time the interview ended. And I finished the remaining steps on my own, post-interview. While I could have written a blog post to walk through my solution, *how* I solved it seems far more important, as that is the paradigm I will reuse in future interviews. 

<iframe src="https://giphy.com/embed/zXmbOaTpbY6mA" width="480" height="203" frameBorder="0" class="giphy-embed" allowFullScreen></iframe><p><a href="https://giphy.com/gifs/technoir-movie-film-cinemagraph-zXmbOaTpbY6mA"></a></p>

<sup>Ah, to live a life where big O notation is wholly insignificant...<sup>
![alt text](/assets/images/IMG_6234.JPG "Meow!")