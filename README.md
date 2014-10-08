# Rails Commands Quiz

Fork, clone, and write your answers directly in this file. Then submit a pull request.

### Question 1 - CORRECT
# Had to check my notes for this one: didn't know if command was 'create' or 'new'

I want to start a new Rails project/app called `BunnyApp`. What command should I type in the terminal?

  $ rails new BunnyApp --database=postgresql

  # CORRECTION: did not have `-T` (without tests)

### Question 2 - WRONG

I want to create a new model called `Bunny`, with the following attributes: name (string), color (string), and age (integer). What command should I type in the terminal?

  $ rails g migrate CreateBunnies name color age:integer

  (I pluralized 'bunny' since we discussed how Rails convention is to make the index and database plural - anything that refers to the entire set of entries. Rails then understands that the singular form is used for a specific single entry.)

  # CORRECTION: should be `rails g migration` not `rails g migrate`.

  # ACCEPTED ANSWERS
  # `rails g model Bunny name color age:integer`
  # `rails g migration CreateBunny name color age:integer`


### Question 3 - CORRECT

What does the command in Question 2 do, exactly? What files are created, where are they located, and what does the database look like at this time? Explain.

  Rails will create a migration file with a numbered file name so that when we run migrations it can keep track of each migration.

  The migration file includes the specs for our columns/attributes for the Bunny database.

  In our migrate command, we specified the attributes name (Rails default is string type), color (Rails default is string type), and age (which we specified as integer type).

  We have not yet run the migration yet, so until we do, the database is not 'anchored' to the application.

  # ACCEPTED ANSWERS
  # rails g model: creates a file /app/models/bunny.rb which defines the Bunny as a Ruby class, AND creates a migration file in db/migrate with the columns and datatypes that were specified in the Terminal command. Doesn't *create* the actual database or *run* the migration.

  # rails g migration: generates a migration - creates a migration file in db/migrate with the columns and datatypes that were specified in the Terminal command. Schema is not created until we run the migration.

### Question 4 - HALF

I want to create a database and make it reflect the new model I created in Question 2. What command(s) should I type in the terminal?

  $ rake db:migrate

  # ACCEPTED ANSWERS
  # rake db:create db:migrate
  # rake db:migrate (will need to create models manually)

### Question 5 - CORRECT
  # Checked notes just to confirm the command was 'rails' and not 'rake'

I want to look at the actual database that has been created. What command should I type in the terminal?

  $ rails db

  # ACCEPTED ANSWER
  # rails db (`rails db` looks at the database; a `\d` once in psql will let you look at the tables.)
  # psql BunnyApp_development (also looks at the database)

### Question 6 - WRONG

I want to see a list of all the URLs available in my app, along with the HTTP requests and controllers associated with them. What command should I type in the terminal?

  $ rails routes

  # ACCEPTED ANSWER
  # rake routes

### Question 7 - CORRECT

I have worked on my app and finally want to see it in action. What command should I type in the terminal, and where should I navigate to in my browser?

  $ rails server

  navigate to the localhost port in our browser, which in our case is:
    localhost:3000/bunnies
    (Using /bunnies here as Rails recognizes that it points to the index view, unless we tell it otherwise.)

    # ACCEPTED ANSWER
    # rails server (or: rails s)
    # localhost:3000 (in your browser) (localhost is an alias our computers have - just a shortcut)
