## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Questions

1. What is the entry at the command line to create a new rails app?

   rails new appname
   
2. What do Models generally inherit from in rails?
  
  Models generally inherit from the ApplicationRecord.  They end up with ActiveRecord inheritance also as ApplicationRecord
  inherits from ActiveRecord.
  
3. What do Controllers generally inherit from in a rails project?

  ApplicationController
  
4. How would I create a route if I wanted to see a specific horse in my routes fitle assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

  horse :resources, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?

  rake routes.  It gives you each verb, route, and URI as well as the controller and action hit.
  
6. What is an example of a route helper? When would you use them?

  company_path.  They're helpful for establishing links in views as well as redirections in the controller.
  
7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

  The `_url` is what will actually be in the navbar(/horse/:id)
  The `_path` is a helper which makes it easier to reference the url.

8. What are strong params and why are the necessary?
  
  strong params are parameters which have been filtered down to only what is needed for the model and controller to use.  They're necessary to prevent users from passing in information that might break the application.
  
9. What role does `form_for` play in helping us create our forms?

  I've only got a high-level understanding of what that does, but I think it directs the form to work for a certain model.
  
10. How does `form_for` know where to submit the user's input?

  The 'Create' button ends up taking the information passed in to the create method for that controller.
  
11. Create a form using a `form_for` helper to create a new `Horse`. 
  <% form_for @horse do |f| %>
    <%= f.label :name %>
    <%= f.text_field :name %>
    <%= f.submit %>
  <% end %>

12. Why do we want to validate our models?
    
    We want to validate our models to ensure that each instance has every desired attribute.
