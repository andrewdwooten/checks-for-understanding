## Week One - Module 3 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

1. What is `json`, what does it stand for, and why is it important?
  JSON stands for JavaScript Object Notation. It is important because it is the
  primary way that bulk information is transferred from from an API. It is both
  machine-readable and also fairly human-readable. We can effectively treat the
  returned JSON from an API call as a hash to grab/format data that we need.
2. What's the difference between `joins` and `includes` in ActiveRecord?
  The joins method will cause a table to be generated on a specified intersection;
  generally this is where the foreign key matches the primary key of another model.
  (User.joins(:invoice)) This is an INNER JOIN operation where the only models returned
  will be Users that have invoices along with their associated invoices.
  The includes method differs from the joins method in that it performs a LEFT OUTER JOIN
  operation, so the above query will return all of the users as well as all invoices that
  are associated with a user.
3. What's an API?
  I had to google what API stands for. Application Program Interface. From my understanding,
  it's a cool little thing-y that acts as a remote interface with a database that a developer
  does not maintain. It allows us to send an http request to the API with xyz parameters and
  have returned to us a JSON object that is the result of a database query within the API.
4. How do we test an internal API (in general)?
  In general, I think of internal API testing as analogous to feature testing. Instead of
  running tests on the views with CSS selectors and whatnot, we simulate requests being sent
  and ensure that the appropriate JSON response is returned.
5. What are two different ways to customize your `json`?
  One way is to use a serializer. A serializer works in association with a model. It can
  control what attributes are presented when an instance of that model is rendered;
  additionally, it can have methods added to it in order to reformat or present
  information that is associated with a model rather than attached to it as an
  attribute. I haven't taken the opportunity to explore implementing these features
  too much as of yet.
  Another way is to use jbuilder. Jbuilder does its work in the views. I'm not
  terribly certain of how it does its work and haven't implemented Jbuilder on
  even a simple level.

#### Review  
6. What is an ORM, what does it stand for, and why is it helpful?  
  An ORM is an object-relational mapper. It acts as a translator piece between
  a language and a database language. ActiveRecord is an example of an ORM. It is
  helpful because it allows developers to write database queries in a more succinct
  and human-readable way than a query written in a raw database language, like SQL.
7. How do you create a record in the following table in SQL? In Active Record?   
   (Users table with columns first_name, last_name, email, and age)
   INSERT in users (first_name, last_name, email, age)
    VALUES (andy, wooten, myemail@email.com, 29) [SQL]

    User.create(first_name: andy, last_name: wooten, email: myemail@email.com, age: 29)[AR]

8. Given an array numbers = [1,2,3,4,5], find the sum of the doubles of all the numbers.  
    a.inject(0){|sum, e| sum += (e * 2)}

#### Self Assessment  
Rate yourself on the following scale.
3. I know and understand most of these concepts but had to look something up  
  I have a decent understanding of most of these topics. I ended up doing some
  google-ing to dig deeper on the joins/includes question as well as to look
  over jbuilder.
