## Week One - Module 2 Recap

Fork this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 1 Questions

1. List the five common HTTP verbs and what the purpose is of each verb.
  Get, Post, Put, Patch, Delete
2. What is Sinatra?
  Sinatra is a domain specific language that allows us to interact with a database using Ruby objects and Ruby logic
4. What is MVC?
  Model, views, controller. It is a way of setting up interactions with a database that adheres to SRP. The model holds most of the logic and relies on representation of raw data as ruby objects. The views are responsible for holding the html, and the controller is responsible for getting information to the database via models and then getting the appropriate html from views before sending that back along to the client via the server.
5. Why do we follow conventions when creating our actions/path names in our Sinatra routes?
  We follow conventions when creating our actions/path names in our Sinatra routes because Sinatra is pre-programmed to expect to find certain things in certain places, so if we don't follow conventions then our Sinatra apps won't work.  Also generally as a good practice it helps make sure that everyone is on the same page and can look at anyone's code and know where to find certain things.
6. What types of variables are accessible in our view templates without explicitly passing them?
  We are able to access any variables that we call immediately in between Sinatra methods that deal with html.  In the controller for example, 'get' and 'erb' are Sinatra methods that pertain to html, so if on one line I call 'get' then I call some ruby code on the next line, and then on the third line I call 'erb' I will be able to access that Ruby from the second line in the erb file.
7. Given the following block of code, how would I pass an instance variable `count` with a value of `1` to my `index.erb` template?

example
  ```ruby
  get '/horses' do
    erb :index
  end
  ```
answer
  ```ruby
  get '/horses' do
    @count = 1
    erb :index
  end
  ```

8. In the same code block, how would I pass a local variable `name` with a value of `Mr. Ed` to the view?
answer
  ```ruby
  get '/horses' do
    @count = 1
    erb :index, locals: { name: 'Mr. Ed' }
  end
  ```
9. What's the purpose of ERB?
Thr purpose of ERB is to allow us to use ruby logic within our html.  This is great for doing things like printing each element of a long array using the same formatting.
10. Why do I need a development AND test database?
You need a development and a test database so that you can make sure you're not polluting your development database with your test features, and so that you can test just one specific piece of functionality at a time in your test database and then wipe it clean.
11. What is CRUD and why is it important?
Create, Read, Update, Delete.  These are the four main actions that people will want to be able to have when they are accessing a database.
12. What does HTTP stand for?
HyperText Transfer Protocol
13. What are the two ways to interpolate Ruby in an ERB view template? What's the difference between these two ways?
You can use <% %> in order to perform ruby logic that you don't actually want to print to the page afterwards, and you can use <%= %> in order to print the returned value of the enclosed ruby to the page.
14. What's an ORM?
Object-Relational Map. It is a way to wrap the database in a programming language.  In our case we use Ruby, and the object classes are mapped to the database tables and the specific instances of that class are mapped to the rows of the database.
15. What's the most commonly used ORM in ruby (Sinatra & Rails)?
The most common setup of the ORM is to create a class that contains attributes which correspond to the columns you wish your database to have.  Then you create instances of that class that represent the rows of the database.
16. Let's say we have an application with restaurants. There are seven verb + path combinations necessary to provide full CRUD functionality for our restaurant application. List each of the seven combinations, and explain what each is for.
  get '/index' - for reading all records
  get '/index/new' - for getting to a page where you can create a new record
  get '/index/id' - for reading information about a record with a specific id
  get '/index/id/edit - for getting to a page where you can modify information about a currently existing record
  post '/index' - for adding the new record to the index
  put '/index/id' - for updating the currently existing record with new information
  delete '/index/id' - for removing the specified record

17. What's a migration?
  A migration is a set of instructions for setting up a database.
18. When you create a migration, does it automatically modify your database?
  A migration does not automatically modify your database when you create it.  You must also run the migration before it takes effect.
19. How does a model relate to a database?
  A model has attributes that correspond to the columns of the database.
20. What is the difference between `#new` and `#create`?
  #create is the same as #new followed by #save.  Just using #new will not actually add the record to the database.

### Review Questions:  
21. Given a CSV file (“films.csv”) with these headers [id, title, description], how would you load these into your database to create new instances of Film?  
  I would create a seeds.rb file that lives in the db folder at the same level as the csv folder and the migrate folder. In the seeds.rb file I would include a line of code that looks like this:
    CSV.foreach('./data/films.csv', headers: true, header_converters: :symbol) do |info|
      Film.create(info)
    end
22. Given the following hash:
```
activities = {
  hiking: {cost: $0, supplies: ['hiking shoes', 'water', 'compass']},
  karaoke: {cost: $10, supplies: ['courage', 'microphone'],
  brunch: {cost: $35, supplies: ['mimosa flutes'],
  antiquing: {cost: $200, supplies: ['list of antique stores']
}
```
How would I add 'granola bar' to things you should have when hiking?
    activities[:hiking][:supplies] << 'granola bar'

23. What are the 4 Principles of OOP? Give a one sentence explanation of each.
Encapsulation means that each object keeps its processes and its attributes to itself to the extent that no other objects require this information.

Data abstraction means that we are able to put a layer between ourselves and the raw data, in this case an ORM which allows us to understand and manipulate the data more easily.

Inheritance means that objects can get all of the general qualities that they share with other objects from a single larger object (superclass) and then they can have their own specific qualities or attributes that make them unique within their own purview.

Polymorphism - means one name many forms and it means that we can have methods with the same name which perform slightly different functions. The function that ultimately is performed depends on the exact way that your program is compiled.


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
