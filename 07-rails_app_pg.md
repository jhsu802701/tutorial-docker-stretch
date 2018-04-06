# Chapter 7: Quick Ruby on Rails App with PostgreSQL

## Topics
* Creating a new Rails app that uses PostgreSQL for the database
* Viewing the Rails app in your web browser
* Viewing your Rails app's database with pgAdmin

## Creating the App
* From the same rails-general directory where you entered the rails-general Docker image, enter the command "sh reset.sh" to return to Docker.
* Enter the command "sh test-rails-pg.sh".  This script runs the info.sh script and then creates a new Rails app.  This app is just like the one in the previous chapter but uses PostgreSQL instead of SQLite.
* The process of creating the new app will take a few minutes.  When it is finished, open your web browser, and go to the URL http://localhost:3000/pupils .  You should now see a form called "Pupils".

## Adding Pupils
* Click on "New Pupil".  For the name, enter "Michael Hartl".  For the form, enter "Rails Tutorial".  Click on "Create Pupil".  Click on "Back".
* Click on "New Pupil".  For the name, enter "Jason Hsu".  For the form, enter "Ruby on Racetracks".  Click on "Create Pupil".  Click on "Back".
* You should now see both of these pupils listed on the web page.

## Using pgAdmin
* In your desktop Linux system, start pgAdmin.
* In the upper left corner of the pgAdmin window, click on the plug icon to add a server.
* Fill in the following server parameters:
  * Name: test_rails_pg
  * Host: localhost
  * Port: 15432
  * Username: user1
  * Password: password1
* In the Object browser, go to Server Groups -> Servers -> test_rails_pg -> Databases -> database1 -> Schemas -> public -> Tables -> pupils.
* Right-click on pupils and select View Data -> View All Rows.
* You should now see entries for Michael Hartl and Jason Hsu.

## Exiting
* Exit pgAdmin.
* In Docker, press Ctrl-C to stop the local server so that you can continue entering commands.
* Enter the command "exit".
