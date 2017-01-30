## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!). 

Note: When you're done, submit a PR. 

1. List the five common HTTP verbs and what the purpose is of each verb.
  get - retrieve a view
  post - update a portion of the view with the given parameter
  put - generate new data and return it in the view.
  delete - delete information
  
2. What is Sinatra?
  Sinatra is a framework language for web development.  My understanding is that it lays out the routes
  and structure for all of the components to interact with each other.
  
4. What is MVC?
  Model View Controller.  I'm uncertain if this refers to all of them as a concept or just the controller.  The controller's        purpose is to delineate the actions that are taken whenever a request is made.
  
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  We follow conventions for the sake of readability and understanding between developers.
  
6. What types of variables are accessible in our view templates without explicitly passing them?
  The parameters of the request I think.
  
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?
  
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
  I'm not sure how to pass a local variable.
  
9. What's the purpose of ERB?
  All of our view files are .erb.  I think the purpose of ERB is to allow you to have a primarily HTML ?document? with ruby injected to bring in data from operations performed in the model.
  
10. Why do I need a development AND test database?
  I suppose having two separate databases allows you to not spend so much memory in storing full sets of data in each and reduces
  the risk in cross-contaminating bad data.
  
11. What's responsive design?
  Responsive design is the concept that a web app should function around an easy user experience across devices.
  
12. What is CRUD and why is it important?
  Create Read Update Delete.  CRUD is important as it represents the options of actions that are available in interacting with    data within our web app.
  
13. What does HTTP stand for? 
  HyperText Transfer Protocol
  
14. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
  <%= ruby-thing %>
  <% ruby-thing %>
  The injection with '=' causes the return of the ruby to be displayed.  I think an exception to being actually displayed would be when we're doing an id thingie. 'stations/<%= station.id %>' It won't necessarily be displayed, but it will be dropped into
the string as '/stations/1'.  The injection without '=' runs the ruby code within it, and we've more used it to manipulate the information that we're going to display to the screen like when we're iterating through each of our stations to display.

15. What's an ORM?
  Object relational mapper.  It seems like it acts as a translator between a database and a object-oriented language like ruby
  .
16. What's the most commonly used ORM in ruby (Sinatra & Rails)?
  ActiveRecord
  
17. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  get '/restaurant' => view the whole list of restaurants
  get '/restaurant/:id' => view a single restaurant
  get '/restaurant/:id/edit' => edit a single restaurant
  put '/restaurant/:id' =>updates the restaurant information and returns the user to the restaurant/:id page.
  get '/restaurant/new' => taken to a page to generate a new restaurant
  post '/restaurant/new' => creates a new restaurant with information provided and takes the user to the restaurant/:id page.
  delete '/restaurant/:id' => deletes selected restaurant and returns user to the '/restaurant' page
  
18. What's a migration? 
  A migration is an object that contains the command to generate or edit a table within your database.
  
19. When you create a migration, does it automatically modify your database?
  No, you have to run rake db:migrate to run your migrations.
  
20. How does a model relate to a database?
  A models attributes should be composed of rows of information stored in cells in the database.
  
21. What's the difference between agile workflow and waterfall method?
  The waterfall method involves blocking out the entirety of a process and proceeding through each stage of development in sequence; it looks like horizontal colored blocks that you're going through left to right.  The agile workflow method rotates the entirety of the blocks 90 degrees; it consists of progressing through each stage of development simultaneously; utilizing this method helps to mitigate the uncertainty of roadblocks in development that might otherwise make a crash-and-burn of the project happen.
  
22. What is the difference between `#new` and `#create`?
  'new' generates a new object containing that attributes which would be the column titles in a database, but does not store it in the database.  'create' does the same thing but also does a 'save' action which stores the information in the database.
