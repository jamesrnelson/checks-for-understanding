## Week Two - Module 2 Recap

Fork or re-pull this respository. Answer the questions to the best of your ability. Try to answer them with limited amount of external research. These questions cover the majority of what we've learned this week (which is a TON - YOU are a web developer!!!).

Note: When you're done, submit a PR.


### Week 2 Questions

1. At a high level, what is ActiveRecord? What does it do/allow you to do?
ActiveRecord is an Object Relational Map which allows us to perform ruby-like actions on our databases.
2. Assume you have the following model:

```ruby
class Team << ActiveRecord::Base
end
```

What are some methods you can call on `Team`? If these methods aren't defined in the class, how do you have access to them?

You can call Team.new, Team.save, Team.create, Team.find(id), Team.destroy, and any other ActiveRecord methods. We can call any ActiveRecord methods on Team because we inherit from ActiveRecord when defining the Team class.

3. Assume that in your database, a team has the following attributes: "id", "name", owner_id". How would you find the name of a team with an id of 4? Assuming your class only included the code from question 2, how could you find the owner of the same team?

team1 = Team.find(4)

team1.owner_id would give you the owner_id. Unless the Team and the Owner are also linked through an ActiveRecord belongs_to method you wouldn't be able to use a method on the Team class that would give you the owner name.

4. Assume that you added a line to your `Team` class as follows:

```ruby
class Team << ActiveRecord::Base
  belongs_to :owner
end
```

Now how would you find the owner of the team with an id of 4?
Team.find(owner_id: 4)

5. In a database that's holding students and teachers, what will be the relationship between students and teachers? Draw the schema diagram.

The relationship between teachers and students is usually a many-to-many relationship because each teacher has more than one student and each student has more than one teacher.

teacher
id

student
id

teacher_students
id
teacher_id
student_id

6. Define foreign key, primary key, and schema.

primary key is a unique auto-incremented key that belongs to a record in a table.
foreign key is a key that links a record in the current table to the primary key of a related record on another table.
schema is the file that shows all of the tables in the database along with all of the columns and how the different tables are linked together.

7. Describe the relationship between a foreign key on one table and a primary key on another table.

The foreign key on one table will be the primary key on the table indicated in the foreign key's name.

8. What are the parts of an HTTP response?

An HTTP Response has a status line which also contains a status code, and response header fields

### Optional Questions

1. Name your five favorite ActiveRecord methods (i.e. methods your models inherit from ActiveRecord) and describe what they do.
.find(id)
.where
.distinct
.group
.joins
.select

2. Name your three favorite ActiveRecord rake tasks and describe what they do.

I liked combining create, migrate, and seed into a single command "rake db:{create,migrate,seed}"

3. What two columns does `t.timestamps null: false` create in our database?
This creates a created_at and an updated_at column in the database.

4. In a database that's holding schools and teachers, what will be the relationship between schools and teachers?
Schools have many teachers and (for the most part) teachers belong to a school.

5. In the same database, what will you need to do to create this relationship (draw a schema diagram)?
You will need to add a school_id to each teacher which will be associated with a school's primary key id.

6. Give an example of when you might want to store information besides ids on a join table.

You might want to store information other than an id on a joins table if you have a specific value (a price for example) that was true only in that shared instance of two separate foreign keys.

7. Describe and diagram the relationship between patients and doctors.

Patients and doctors is usually a many-to-many relationships.

8. Describe and diagram the relationship between museums and original_paintings.
The relationship between museums and original_paintings is a one-to-many relationship because

9. What could you see in your code that would make you think you might want to create a partial?
If you start seeing the same html in several views, then it's probably a good idea to see if you can pull some of this shared html out to a separate file in order to aboid repeating ourselves.

### Self Assessment:
Choose One:
* I was able to answer every question without relying on outside resources


Choose One:
* I feel confident about the content presented this week
