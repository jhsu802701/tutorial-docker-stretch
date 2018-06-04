# Chapter 8: Rails Tutorial Sample App
[** Click here for Chapter 7 ** ](https://github.com/rubyonracetracks/tutorial-docker-stretch/blob/master/07-rails_app_pg.md)
In this chapter, you will download and run Michael Hartl's Rails Tutorial Sample App.  You will learn to use tmux.  In the interest of saving time, the rails-general Docker image comes preinstalled with the latest version of Ruby and the versions of the rails, pg, and nokogiri gems specified in the Rails Tutorial Sample App.

## What's the point?
* tmux allows you to split your Docker window into multiple windows so that you can perform several tasks simultaneously.
* You will use one tmux window to run the local Rails web server, one tmux window for running the Rails sandbox, one tmux window for running Guard, and one tmux window for entering commands.

## Downloading the Source Code
* From your desktop Linux setup, enter the command "sh reset.sh".
* Enter the following command:
```
git clone https://bitbucket.org/railstutorial/sample_app_4th_ed.git
```

## Starting the Server
* Enter the command "tmux".
* Enter the following commands:
```
cd sample_app_4th_ed
bundle install; rails db:migrate; rails test; rails s -b 0.0.0.0 -p 3000
```
* It will take a few minutes for the Sample App to be set up and tested.  All tests should pass.
* After the setup process has been completed, the Rails server will be activated.  In your web browser, go to http://localhost:3000/ to view the Sample App.

## Starting the Rails Sandbox
* In Docker, press Ctrl-b and then press "c".  This creates a new tmux window and puts you in it.
* Enter the following commands:
```
cd sample_app_4th_ed
rails console --sandbox
```
* You are now in the Rails sandbox.
* Enter the command "Micropost.all".  You'll see some screen output but no actual microposts.
* Enter the command "User.all".  You'll see some screen output but no actual users.

## Seeding the Database
* Press Ctrl-b and then press "c".  This creates another new tmux window and puts you in it.  Window 0 is dedicated to the Rails server, and Window 1 is dedicated to the Rails sandbox.
* Enter the following commands:
```
cd sample_app_4th_ed
rails db:migrate:reset; rails db:seed
```
* It will take a few minutes for the Sample App to finish seeding the database with fake data.

## Viewing Data in Rails Sandbox
* To view the next tmux window, press Ctrl-b and then press "n".
* To view the previous tmux window, press Ctrl-b and then press "p".
* Use the above tmux actions to return to Window 1, the tmux window dedicated to the Rails sandbox.
* In order to update what Rails sandbox shows, you must exit it and then restart it.  Enter the command "exit", and then enter the command "rails console --sandbox".
* Enter the command "Micropost.all".  You will now see a list of all microposts.
* Enter the command "User.all".  You will now see a list of all users.

## Starting the Guard Server
* NOTE: I don't agree with the use of the automated test tool Guard, but it's a good example of how tmux can be used.
* In Docker, go to Window 2 (where you seeded the database).
* Enter the command "bundle exec guard" to start the Guard server.
* Once Guard has started up, press the Enter key again to run the tests, which should all pass.
* In your desktop Linux system, edit the app/models/micropost.rb file in the sample app project.  Change the maximum length of the content from 140 to 1.
* Check the Guard window (Window 2) in Docker.  You'll see that the micropost model test now fails.
* In Docker, press Ctrl-b and then press "c" to create a new tmux window (Window 3).
* Enter the command "cd sample_app_4th_ed; git status".  Note that the app/models/micropost.rb has now changed.
* Enter the command "git checkout app/models/micropost.rb".  This removes the change you just made.
* In Docker, press Ctrl-b and then press "p" to return to Window 2 (Guard window).  You'll see that the micropost model test now passes again.

## Exiting
* In Docker, press Ctrl-b and then press "n" to return to Window 3.  Enter the command "exit" to close this window.  You should now be in Window 2.
* Enter the command "exit" in Window 2 to exit Guard.  Enter "exit" again to close Window 2.  You should now be in Window 1.
* Enter the command "exit" in Window 1 to exit the Rails sandbox.  Enter "exit" again to close Window 1.  You should now be in Window 0.
* Press Ctrl-c to stop the Rails server.  Then enter the command "exit" to close Window 0 and leave tmux.
* Enter the command "exit" to leave the Docker container.

## Conclusions
* Congratulations!  You now understand how to use Docker under the Ruby on Racetracks way.
* For every Rails project that I'm on, I provide a custom Docker image that includes the correct versions of Ruby, the Rails gem, and certain other gems.  This makes the setup process much faster and shorter.
* In my tutorials involving specific projects, you will use the offset values for the port numbers.  Thus, the port numbers of a Rails project will be different from the ones used in this chapter.  Using a different offset value for different Docker containers allows you to run multiple Docker containers simultaneously.  If a Docker container you are running uses any ports, trying to start a second Docker container will lead to error messages due to the conflict.
[** Return to the README here ** ](https://github.com/rubyonracetracks/tutorial-docker-stretch)
