# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1
# Had to check my notes for this one: didn't know if command was 'create' or 'new'

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

  $ rails new BunnyApp --database=postgresql

### Question 2

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command should I type in the terminal?

  $ rails g migrate CreateBunnies name color age:integer

  (I pluralized 'bunny' since we discussed how Rails convention is to make the index and database plural - anything that refers to the entire set of entries. Rails then understands that the singular form is used for a specific single entry.)


### Question 3

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

  Rails will create a migration file with a numbered file name so that when we run migrations it can keep track of each migration.

  The migration file includes the specs for our columns/attributes for the Bunny database.

  In our migrate command, we specified the attributes name (Rails default is string type), color (Rails default is string type), and age (which we specified as integer type).

  We have not yet run the migration yet, so until we do, the database is not 'anchored' to the application.

### Question 4

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

  $ rake db:migrate

### Question 5
  # Checked notes just to confirm the command was 'rails' and not 'rake'

I want to look at the actual database that has been created. What command should I type in the terminal?

  $ rails db

### Question 6

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

  $ rails routes

### Question 7

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

  $ rails server

  navigate to the localhost port in our browser, which in our case is:
    localhost:3000/bunnies
    (Using /bunnies here as Rails recognizes that it points to the index view, unless we tell it otherwise.)

