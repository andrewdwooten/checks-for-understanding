## Week Two - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!). 

Note: When you're done, submit a PR. 

1. At a high level, what is ActiveRecord? What does it do/allow you to do?

  ActiveRecord is kind-of a translator piece that allows us to interact with a database using Ruby.
  
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

  Team.all, Team.first, Team.last, Team.find_by(attribute: value), Team.count.  These methods are inherited from ActiveRecord.
  
3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?
  
  name = Team.find_by(id: 4).name
  owner_id = Team.find_by(id: 4).owner_id
  Owner.find_by(id: owner_id)
  
  

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
  owner = Team.find_by(id: 4).owner
  
3. What do they allow you to do?

  The belongs_to line established a relationship, for ?Active Record?, between the Team and the Owner, so it allows you to call
  .owner on a team and ActiveRecord references the database for with the owner_id to return the Owner.
  
7. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

  It's going to be a many-to-many relationship; I'm not sure how to draw the schema diagram in this box, but I think with that relationship it could involve a table like Students_Teachers that holds rows of each student matched to each teacher based on foreign keys.
  
  
8. Define foreign key, primary key, and schema.

  A primary key is the unique ID of a row(which is an instance of a model/object).
  A foreign key is a primary key that is dropped into another table with '_id' after it to allow for linking between those    instances.
  A schema is the skeleton of your database that defines all of the columns in each with their names as well as the kind of information it is(string, integer, etc).  You never edit it directly.
  
9. Describe the relationship between a foreign key on one table and a primary key on another table.

  If I'm understanding the question correctly, the two should be equal values.  The foreign key allows for reference to the row by looking for the primary key that matches the foreign key.
  
10. What are the parts of an HTTP response?

  The request is sent to the controller.  From there, the controller talks to the model, giving it parameters.  The model talks to the database to get what it needs.  This is returned to the controller which then passes that information to the assigned view which is rendered with that information.
  
11. Describe some techniques to make our Sinatra code more DRY. Give an example of when you would use these techniques.
  I understand that DRY is an acronym for 'Don't Repeat Yourself', and I'm sure I've applied the principle at points, but I'm not sure of a specific technique or example.

### Optional Questions
    (I didn't answer any I didn't have an answer in my head for.)

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.

  find_or_create_by: it will retrieve the row in the database you're looking for or create it with the parameters given.
  first & last: they bring back, respectively, the first and last entries in a table.  They're handy for checking that things are working properly.
  order: it returns the collection but organzied by a specified parameter.
  average: it will average a column of the table.  I appreciate not having to math it out in ruby.
  where: it will return an array of rows/instances that match the search parameters.
  
2. Name your three favorite ActiveRecord rake tasks and describe what they do.

  db:seed => It follows the instructions in the seeds file and populates your tables with data.
  db:migrate=> It builds out the database with tables defined in migration files, or updates it with the new migrations.
  db:drop=> It sets everything back to zero; no more database/tables/data.  I don't know why this is my favorite, but it's      something that was fun to do during Bikeshare.
  
4. What can you expect from a group as you begin working together? As you continue working together?
    I wouldn't say that I expect much.  I hope for a lot of things.
    
    Members of a group will be open and honest about their expectations and wants for a given project.
    They will define parameters for working conditions(morning, night, screenhero, paired, etc.)
    In continuing on, I hope they'll be open with feedback and quickly resolve any conflicts that arise.
    Team members will be open with the group when they don't understand something or are struggling.
    Team members will be mutually respectful of each other and their work.
  
  
5. What two columns does `t.timestamps null: false` create in our database?

  It creates the 'created_at' and 'updated_at' columns.
  
6. What cURL flag can you use to send a `POST` request?
7. What case does JSON (and JavaScript) use for multi-word variables?
8. What case does Ruby use for multi-word variables?

  snakecase: multi_word_variable
  
9. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?

  One to many relationship(school:teachers)
  
10. In the same database, what will you need to do to create this relationship (draw a schema diagram)?

  The teacher name will need the foreign key for the school they're assigned to.  The models will have to have the relationships defined.  Teacher will 'belong_to' a school, and a School will 'have_many' teachers.
  
11. Give an example of when you might want to store information besides ids on a join table.
12. Describe and diagram the relationship between patients and doctors.

  I think it would best be represented by a many-to-many relationship.
  
13. Describe and diagram the relationship between museums and original_paintings.

  I think it would be best represented by a one to many relatipnship.
  
14. What are some examples of acceptable values for the parts of an HTTP response?
15. What types of output do we want to test when we test our controllers?
16. What could you see in your code that would make you think you might want to create a partial?

  A form that crops up in multiple places, like an edit and new.
  
17. Why might you use a helper method?
