## Week Three Recap

### Instructions
Fork this repository. Be sure to pull the latest changes to your local repo. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 3 Questions

1. What is the entry at the command line to create a new rails app?

rails new name_of_app -T -d="postgresql" --skip-turbolinks --skip-spring

2. What do Models generally inherit from in rails?

Models inherit from ApplicationRecord in rails.

3. What do Controllers generally inherit from in a rails project?

Controllers inherit from ApplicationController in rails.

4. How would I create a route if I wanted to see a specific horse in my routes file assuming I'm sticking to standard conventions and that I didn't want other CRUD functionality?

In the config/routes.rb file type:
resources :routes, only: [:show]

5. What rake task is useful when looking at routes, and what information does it give you?

'rake routes' will tell you all of the routes that are currently available to you based on the routes in the config/routes.rb file.

6. What is an example of a route helper? When would you use them?

edit_model_path(model) is an example of a route helper.  This is what you would use to visit the edit page for a specific model (indicated in parentheses).

7. What's the difference between what `_url` and `_path` return when combined with a routes prefix?

When combined with the routes prefix, `_url` will give you the entire url including http:// and `_path` will give you just the specific uri within your current domain.

8. What are strong params and why are they necessary?

Strong params are a way to limit the types of parameters that you accept from the client when creating or editing a database record.

9. What role does `form_for` play in helping us create our forms?

form_for allows us to easily create forms for updating and editing records in the database.  It is also responsive to whichever path it is on, so as a partial it will change itself to see Create or Edit based on whether the file that it is being used in is a new.html.erb or an edit.html.erb.

10. How does `form_for` know where to submit the user's input?

form_for knows where to submit a user's input because it knows whether it is a new entry or an edit entry, and it knows the specific id of any item that it may be editing.

11. Create a form using a `form_for` helper to create a new `Horse`.

<%= form_for @horse do |f| %>
  <%= f.label :name %>
  <%= f.text_field :name %>
  <%= f.label :breed %>
  <%= f.text_field :breed %>
  <%= f.submit %>
<% end %>

12. Why do we want to validate our models?

We want to validate our models so that we know that all of our models will have the required attributes in order to create a model successfully.

13. What are the steps of the DNS lookup?

First, the DNS server looks at your computer's cache to see if it already has an IP address match for the requested domain name.  If it's not there, it checks the router's cache, then the ISP's cache, then the root servers, then the TLD name servers.


### Review Questions

14. How would you call the method `prance` from within the method `move` on a `Horse` instance?

horse.move.prance

15. Given the following hash:

```ruby
furniture = {table: {height: 3, color: "red"}, purchased: true}
```
What is the different between how you would return true vs returning 3?  

furniture[:purchased] would return true
furniture[:table][:height] would return 3

16. What is inheritance?

Inheritance is a way to gain access to the methods of a class's superclass without explicitly defining those methods in the class.

### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel confident about the content presented this week
