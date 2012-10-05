Heroku descaler
===============

There are 2 rake tasks to scale up or down web processes on heroku.

Use case that I am using it for, involves installing this code on heroku itself and via [heroku scheduler](https://devcenter.heroku.com/articles/scheduler) scaling web processes of another app based on time of the day. 

To scale up
    
    rake scale_up

and to scale down, surprise, surprise
    
    rake scale_down

Environment variables that need to be set before running:
---------------------------------------------------------

HEROKU_APP that you would like to scale

HEROKU_API_KEY that belongs to privileged account

NUMBER_WHEN_UP - number of web processes when scaled up

NUMBER_WHEN_DOWN - number of web processes when scaled down
