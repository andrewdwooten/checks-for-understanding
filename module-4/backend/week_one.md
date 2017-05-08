## Week One - Module 4 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week. 

Note: When you're done, submit a PR. 

1. What's the most useful thing you learned from completing the intermission week work?
  The most useful thing I learned during intermission week were the basics of JS;
  Sorting Suite as well as the lessons provided were awesome at helping me start building
  some habits and get some familiarity going.
2. What are some tools to help debug JavaScript code?
  console.log();
  debugger;
  eval(pry.it);  <= Yay for having pry!
3. What are some tools you need in order to unit test your JavaScript?
  The mocha module and the chai module as well as knowing how to export/require
  files in JS. I would also add that having the chai docs open is immensely helpful.
4. What is the syntax for invoking a function?
  functionName();
5. What's the difference between `==` and `===` in JavaScript?
  == does a less in depth comparison than ===: 5 == '5' => true vs. 5 === '5' => false
6. What's the difference between asynchronous and synchronous JavaScript? 
  I think of synchronous JS as running in sequence and not being able to move on to another
  task without having the first task accomplished; asynchronous JS allows us to execute some function,
  like an API call, and then work on something else while we're waiting for something 'slow' to come back.
7. What's a callback function and what are some reasons when we use/need callback functions?
  A calback function is a function passed to another function as an argument(kinda?).
  $('#my-element').click(callbackFunction(){
    do a thing
    });
    We use callback functions in jQuery to describe what is to be done when an event listener is
    triggered.
8. What's the biggest difference between a promise and a callback?
  The word then, and I think they allow a basis for asynchronous JS as they 
  will execute when the data is received but will not cause a program to pause while
  it waits on the necessary information to execute the promise.
9. How do we setup a route when creating an API with Node and Express?
  Carefully.
  app.get('/api/foods/:id', function(request, response){
  var id = request.params.id;
  var food = app.locals.secrets[id];
  if(!food){return response.sendStatus(404);}
  response.json({ //tests are passing but looking at it now, I'd like to re-evaluate how these last two lines work.
    food: food
  });
});
10. What's `npm` and what do we use it for?
  Node Package Manager. We use packages as we do gems in Ruby. 

#### Review  
11. What's the MVC design pattern? Describe each part of MVC?
  Model-View-Controller.
  The controller is a router. When a route in a controller is requested, the controller digs for the correct information and gives it to the view to render.
   The model is an object that represents a table with a row being a single instance of the model. When necessary, the model will access the database to return necessary information that is requested by the controller and pass it along to the same.
   The view is the framework and styling that the client renders. It generally contains placeholders for variable information that will be filled in with the return from a database call made by a model.
12. What is AJAX? What are some benefits of using AJAX?
  Asynchronoush Javascript and XML.  They are incredibly fast for hitting an API and rendering the return as desired as opposed to a Ruby service doing the same job; this is a great performance enhancer for an application; I couldn't believe the speed increases as opposed to the other way. In my use case, it also allowed me to keep my views cleaner in my Rails app as the information from the AJAX call was appended to the view rather than built into it.
13. What's a background worker? When would we want to use a background worker?
  A background worker is kind of a thing-y behind the scenes that can be passed a queue of tasks to complete with a timeframe as to when to complete them. We would want to implement one at a time when a slow process was bogging down time affecting user experience; rather than carry out a slow process and force are user to wait to keep using the application we can pass it to a background worker that will complete it while the user carries on with user-ing.
