Mountain Operations Observatory Logging
=======================================
After my experience with the [bok-logging system](https://github.com/so-mops/bok-web-logger/), I decided a standardized way of logging would be usefull. Thus the [mtnops-logger](https://github.com/so-mops/mtnops-logger) was born. Instead of using django as I did at Bok, I decided to separate the web stuff from the logging and use sqlalchemy as the database ORM. These loggers are now running at VATT, Kuiper and Bok. 
