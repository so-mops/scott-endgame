Logging and web display at the Bok Telescope
============================================
The weather web display and logging at Bok uses django for both server side scripting and a SQL ORM. It is a rather old version of django and uses python2.7. In logging and web utilities at other telescopes I have switched to flask for the server side scripting and sqlalchemy as the ORM.  The source for logging and web display is split up into two repositories:

1. [The django source](https://github.com/so-mops/bok-web-logger)
2. [The logging script](https://github.com/so-mops/bok-logger)

You can see the web display [here](http://bok.as.arizona.edu:42080/bokdev/bokdev/) along with everything that is being logged [here](http://bok.as.arizona.edu:42080/bokdev/bokdev/latest_new.json). 

Maintenance and Bugs
--------------------

This software has been pretty solid over the last several years. It has changed very little since 2017 and continues to display and log. 

### Issue List
1. [The database gets so big, accessing it becomes very slow.](https://github.com/so-mops/bok-web-logger/issues/1)



Future Direction
-----------------
