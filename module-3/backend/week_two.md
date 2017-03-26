## Week Two - Module 3 Recap

Fork this repository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

* What's OAuth?
  OAuth is an authorization platform(?) that allows us to utilize already existing authorization
  from a third-party(GitHub, Facebook, Twitter, etc) to authorize/authenticate a user in an
  application.
* What are some advantages/disadvantages of implementing OAuth?
  As advantages: With OAuth we allay some concern over holding on to sensitive user information in our
  database, passing on that responsibility to the third-party. It also streamlines the log-in process
  somewhat, which is really spiffy.
  As disadvantages: It can be kind of a pain to implement correctly; also, depending on the user information
  that the third-party stores on the user, it may be necessary to gather additional desired user information from
  the user.
* How many exchanges of information need to take place before a user is authenticated with OAuth?
  I'm a little unclear on this. The user clicks 'login with github'
  and is directed to github where they click again to authorize
  our application to access their information; the request
  is tagged with our applications client_id and client_secret. From their github sends information to the registered
  callback url. This contains an access token as well as user information. We use this information
  to update or register the user with our application and then they're logged in.
* Why do we want to create services?
  Services, in my mind, allow for maintaining SRP throughout an application.
  We could put these methods into a model or another PORO of some kind, but
  that seems like it would get ugly pretty quickly. A service is a special-purpose
  object; in our case thus far we've used them to handle the entirety of the
  Faraday calls to an external API.  
* Why is it good practice to create PORO's with the data received from an API?
  I think it is a good practice because, again, it maintains SRP. Our service
  receives the raw JSON feedback from an API request. Each PORO, designated
  for a particular set of requests, then handles that data and, in my use,
  formats it to the end pieces that I really want from the request. This makes
  it easier in future development to make modifications in each piece(model,
    poro, and service) to achieve the desired functionality.
* What do we use VCR for? Why is a good idea to use this tool?
  VCR allows us, in testing, to record the response received from an API
  request and then replay it as many times as we run our test suite. It's a
  good idea to use this tool for a few reasons. It makes for a static input
  for the test to run against; in the case of GitHub it makes it such that
  my making new repositories will not break previous tests that were contingent
  on the repository count, order, etc. This gets more important when dealing with
  an API that is subject to large amounts of change in the output(Reddit, Twitter,
  Facebook, etc). Any given API may also have a limit on the number of requests
  a client is allowed to have in a given time period. VCR testing helps to
  ensure that we don't go over this number and get locked out until our
  requests are refilled; this is no fun at all if you're trying to get some
  work done. Finally, VCR testing speeds up the run of our test suite as it
  is calling the saved cassettes rather than having to send API requests for the
  purposes of running the test. In my implementation, I generally saw a ten-fold
  increase in the speed of running my test suite. Obviously, this has great
  implications for it's implementation on a larger scale if that trend holds
  true with increased scale.
