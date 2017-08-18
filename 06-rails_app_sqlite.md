# Chapter 6: Quick Ruby on Rails App with SQLite

In this chapter, you will create a quick Ruby on Rails app that uses SQLite for its database.

## Topics Covered
* Creating a new Rails app that uses SQLite for the database
* Viewing the Rails app in your web browser
* Viewing your Rails app's database with the SQLite Browser

## Creating the App
* Enter the command "sh reset.sh" to return to Docker.
* Enter the command "sh test-rails-sq.sh".  This script runs the info.sh script and then follows the procedure from http://elinux.org/RPi_Ruby_on_Rails for creating a new app.
* The process of creating the new app will take a few minutes.  When it is finished, open your web browser, and go to the URL http://localhost:3000/pupils .  You should now see a form called "Pupils".

## Adding Pupils
* Click on "New Pupil".  For the name, enter "Rod Serling".  For the form, enter "The Twilight Zone".  Click on "Create Pupil".  Click on "Back".
* Click on "New Pupil".  For the name, enter "George Romero".  For the form, enter "Tales from the Darkside".  Click on "Create Pupil".  Click on "Back".
* You should now see both of these pupils listed on the web page.

## Using SQLite Browser
* In your desktop Linux system, open SQLiteBrowser (which you installed during the Docker installation process).  Go to File -> Open Database, and open the db/development.sqlite3 within your app.  (The directory tree is jhsu802701 -> docker-debian-stretch -> rbenv-general -> shared -> school_sq .)
* Go to the "Browse Data" tab.
* Change the "Table" setting to display "pupils".
* You should now see the entries for Rod Serling and George Romero.

## Exiting
* Exit SQLite Browser.
* In Docker, press Ctrl-C to stop the local server so that you can continue entering commands.
* Enter the command "exit".
