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
This project was fairly early on in my career at Mountain Ops. It uses old versions of django and python. I would recommend replacing instead of modifying it in the near future. Luckily for you I have begun that very process. 

In early 2018 I started working on a [new mtnops-logger](https://github.com/so-mops/mtnops-logger) that I have started deploying at the VATT, the 61" and even a little bit at Bok. It uses flask and sqlalchemy instead of going all in on django. At Bok, the only thing currently being logged with this new system is the RA Oil pressure sensor. The module that defines the database is and the getdata function is [here](https://github.com/so-mops/mtnops-logger/blob/master/src/mtnopslogger/boklog/ra_oil.py) and the logging script is [here](https://github.com/so-mops/mtnops-logger/blob/master/scripts/boklogging.py). 

It runs on a raspberry pi in the network closet next to the control room. I am likely the only one who remembers this. The reason I didn't put it on bokpop with the its predecessor is bokpop is too old to run the more modern python. Someone will have to to take the definitions in [models.py] and add them to modules in the new [mtnops-logger boklog directory](https://github.com/so-mops/mtnops-logger/tree/master/src/mtnopslogger/boklog).
