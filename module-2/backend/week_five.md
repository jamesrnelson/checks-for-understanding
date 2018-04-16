### Week 5 Questions

Re-pull from this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON!).

Note: When you're done, submit a PR.

### Week 5 Questions
1. How do we make flash messages display on a page?
  * We make flash messages display on a page by adding a flash notice into the controller that manages the action that you want to display a notice about.

2. Where is cart information/temporary information usually stored?
  * Cart information/temporary information is usually stored in the session hash.

3. What might be some reasons not to store a cart in our database? Are there any reasons why we would want to persist that information?
  * You might want to store a cart in the database in order to allow a registered user to come back and complete the order at a later date.

4. What is the purpose of the asset pipeline?
  * The purpose of the asset pipeline is to minimize the number of unique requests the client must make in order to get all of the components of a website.

5. Why do we precompile our assets?
  * We might precompile our assets in order to ensure that we have immediate access to all of the outside resources we relied upon to create our website. This can help ensure against these resources moving or existing in obscure locations, both of which would slow down the client's experience using our site.

6. What do each of the following tags do?

```ruby
<%= stylesheet_link_tag "application" %>
<%= javascript_include_tag "application" %>
<%= image_tag "rails.png" %>
```

7. What are some of the elements of a great read me? What are some of the benefits of taking the time to update a readme for our project?
  * A great readme would have good organization, provide good examples and code snippets of how the program works, provide only the information we need without going overboard on unhelpful details.

8. What are the top four accessibility issues that we as developers should be aware of?
  *

9. `before_save` is an example of a what? Where in our Rails application would we find a `before_save`?
  * This is an example of a callback. We would find a call back at the model level, and it is used to perform an action before a new record aligning with that model is saved into the database.

10. Given the following object, how would we create a scope for all users who are active?
  * User.where(active: true)

```ruby
User.create(name: "Happy", active: true)
```

11. What is the difference between a scope and a class method?
  * A scope would be a collection of instances of a class. You can use class methods on a scope of the class just as if you were trying to call the class method on the entire class.


### Review Questions:  
12. Given the following hash:  

```ruby
{cart: {"17" => 4, "204" => 52, "29" => 22}}
```

  12a. How would you add item with id of 48 with a quantity of 4?  
    * hash[:cart]["48"] = 4
  12b. How would you increase the quantity of item 29?
    * hash[:cart]["29"] = new_value
  12c. How would you find out how many items your user is thinking about purchasing?   
    * hash.values.sum

13. What is polymorphism? How does it relate to duck-typing? What are two ways you use this in everyday Rails applications?  
  * Polymorphism is the quality of an object looking like and acting like another object. For example, ActiveRecord associations are technically not arrays, but since they look and act like arrays we are able to treat them like arrays.
14. How would you clean the string "(630) 854-5483" to "630.854.5483"?  
  * string.delete('()').split(/[ -]/).join('.')


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel comfortable with the content presented this week
