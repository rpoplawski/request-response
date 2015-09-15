This folder structure should be suitable for starting a project that uses a database:

* Fork this repo
* Clone this repo
* Run `bundle install` to install `active_record`
* `rake generate:migration <NAME>` to create a migration (Don't include the `<` `>` in your name, it should also start with a capital)
* `rake db:migrate` to run the migration and update the database
* Create models in lib that subclass `ActiveRecord::Base`
* ... ?
* Profit

1) On the command line, type 'ruby bin/run.rb'. Then press 'enter'. Type 'GET http://localhost:3000/users HTTP/1.1' and you should see ALL of the users from the database printed out to me with an appropriate response code. Type 'ruby console.rb'. Then press 'enter'. This will take the user into 'pry'. Next, type 'User.all' and press 'enter'. This will give the output of the database.

2) On the command line, type 'ruby bin/run.rb'. Then press 'enter'. Type 'GET http://localhost:3000/users/1 HTTP/1.1' and you should see ONLY the user from the database with that id. Type 'ruby console.rb'. Then press 'enter'. This will take the user into 'pry'. Next, type 'User.all' and press 'enter'. This will give the output of the database.

2) On the command line, type 'ruby bin/run.rb'. Then press 'enter'. Type 'GET http://localhost:3000/users/9999999 HTTP/1.1' and you should see a message saying it was not found and the appropriate response code returned.
 Type 'ruby console.rb'. Then press 'enter'. This will take the user into 'pry'. Next, type 'User.all' and press 'enter'. This will give the output of the database.


## Rundown

```
.
├── Gemfile             # Details which gems are required by the project
├── README.md           # This file
├── Rakefile            # Defines `rake generate:migration` and `db:migrate`
├── config
│   └── database.yml    # Defines the database config (e.g. name of file)
├── console.rb          # `ruby console.rb` starts `pry` with models loaded
├── db
│   ├── dev.sqlite3     # Default location of the database file
│   ├── migrate         # Folder containing generated migrations
│   └── setup.rb        # `require`ing this file sets up the db connection
└── lib                 # Your ruby code (models, etc.) should go here
    └── all.rb          # Require this file to auto-require _all_ `.rb` files in `lib`
```
