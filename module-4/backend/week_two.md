## Week Two - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What is Webpack and why is it useful?
  Webpack is the asset pipeline in JS-land. It is helpful because it makes it such that you don't have to require each file individually that you would need; rather, you can configure Webpack to grab and pre-process all of the files you need to run into a single file.
2. When do you want to use event delegation?
  I don't recall if we did the event delegation lesson or not; it doesn't look familiar in looking over the lesson. Event delegation is a methodology that allows for bypassing of adding and removing event listeners based on the presence of the monitored node. It sounds like you would do that instead of attaching and removing a listener from nodes that may or may not be in the DOM. This is kinda fuzzy but sounds pretty neat.
3. What's one difference between ES5 and ES6?
  You can do string interpolation in ES6, which is super-spiffy and makes is a lot easier to look at and work with than concatentation.
4. What's the deal with semi-colons in JavaScript?
  They're not necessary for things to run correctly and seem like they're more a style choice than anything. People get opinionated about them.
5. How are you using the MVC design pattern in your Quantified Self project?
  In driving out the API endpoints, it was a very familiar pattern. Test --> add route --> test --> add method to controller -->test --> add method to model --> test(will pass after necessary debugging process of model, controller, route, and test.
6. How do you execute raw SQL in node?
  Carefully. `database.raw('SELECT * FROM sql_table')`
7. What is CORS?
  Cross-origin resource sharing. To my understanding, it is the ability of one web application to obtain and use resources from another.
8. What are some steps to avoid CORS?
  `const cors = require('cors');

  app.use(cors({origin: '*'}))`
  
  Add that in the right spot. I'm uncertain if this is in conjunction with or instead of modifying the headers with the  `Access-Control-Allowed-Origin:` piece.

#### Review  

9. Why do people say "HTTP is stateless"?
  HTTP is considered stateless because each request is considered as an individual request without information persisting between each except possibly things stored in the cookies or session.
10. What is a RESTful API?
  I'd like to learn more about RESTful-ness at some point. An API allows for accessing an external database via HTTP requests. The best answer that I presently understand about RESTful-ness is that a specific request will always return the same thing. It seems like there is also a good bit of convention regarding route naming, which makes life substantially easier because you can rely on what is likely going to be returned from a certain route.
11. What are some main characteristics of a team following an agile workflow?
  I always think of regular stand-ups, completion of iterations, and a problem-attack pattern that focuses on completing the whole problem at hand rather than attacking in a linear fashion that might require the team to go back and re-do work.
12. What are some advantages/disadvantages to using OAuth to authenticate a user?
  Advantages can include not having sensitive user data and having a streamlined log-in process by using a common social media log-in. Disadvantages can be essentially barring some users from log-in if they do not have the OAuth account in question and not being able to have the data we would like without specifically requesting it either from the OAuth provider or from the user during registration.
