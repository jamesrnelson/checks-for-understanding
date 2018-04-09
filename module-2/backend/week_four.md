## Week Four Recap

### Instructions
Fork or re-pull this repository. Answer the questions to the best of your ability.

Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week.

Note: When you're done, submit a PR with a reflection in the comments about how this exercise went for you.

### Week 4 Questions

1. What is a cookie?

A cookie is a file containing information that helps a website keep track of a browser's identity. The website gives the file to a user's browser so that the browser can send it back to the website with each http request in order to help provide a personalized user experience.

2. What’s the difference between a session and a cookie?

The difference between a session and a cookie is that session data is stored on the server and then deleted when the session ends and a cookie is stored in the client's browser.

3. What’s a flash and when do you want to use flashes?

A flash is a notification that shows up on a page that isn't otherwise in the html for that page. You want to use them when a user is trying to do some sort of destructive action to confirm that this is really what they want to do. You also want to use a flash informing the user if their action has been successful or not (and if not, why).

4. Why do people say “HTTP is stateless”?

HTTP is stateless because it doesn't keep track of an ongoing conversation.  It's like it has amnesia; it only knows exactly what you tell it each time you talk to it.

5. What’s authentication? Explain.

Authentication is making sure that a person is who they say they are.  In terms of login information this is to ensure that only the person whose account it is can access that account.

6. What’s the difference between authentication and authorization?

Authentication is used to make sure that a person is who they say are, but authorization is for giving specific people access to limited sections of the site, such as admin capabilities that may come with additional CRUD functionality.

7. What’s a before filter?

A before filter is a method that you can run before each method within a specified class in order to ensure that only a person with the appropriate authorization is able to actually carry out that method.

8. How do we keep track of a user once they’ve logged in?

Once a user is logged in, we keep track of them using the session hash that we get from rails. We also define some helper methods such as current_user and current_admin? to help us make the session hash even more powerful.

9. When do you want to namespace a resource? When do you want to nest a resource? What's the differences between those two approaches?

You want to namespace a resource when you want to limit access to certain parts of the site to an admin. You want to nest resources when the nested resource is only ever accessed within the context of the first resource.

10. At a high level, what tools can you use to implement authorization? How would you use them?

In order to implement authorization you want to create separate parts of the website that are only accessible to the admin (namespacing) and you want to add a double check before each of the things that an admin is able to do that verifies that the person trying to do this admin thing is indeed an admin.

11. What's an enum, and what advantages does it offer? What data type needs to be in your database to use an enum? Where do you declare an enum?

An enum correlates an integer value with a hash of predefined values. The enum's data type needs to be an integer.

12. What are some strategies you can use to keep your views DRY?

You can use partials of sections of code that you use on several views and then just reference those partials instead of typing out all the code each time.


### Reviews Questions
13. Given the following array of hashes, how would I print an alphabetical list of holidays?
```ruby
[
 {holiday: {name: "St Patrick's Day", supplies: ["Corned Beef and Cabbage"]},
 {holiday: {name: "Halloween", supplies: ["Candy", "Costume"]},
 {holiday: {name: "Hanukkah", supplies: ["Menorah"]}
]
```
array.sort_by { |holiday| holiday[:name] }


14. How would you clean incoming data to ensure "$300" or "300.00" is stored as 300?

cleaned_data = incoming_data.delete('$').to_i


### Self Assessment:
Choose One:
* I was able to answer most questions independently, but utilized outside resources for a few

Choose One:
* I feel confident about the content presented this week
