Telcom Server
=============

The windows based legacy TCS designed by Dave Harvey used RS-232 serial lines to allow remote access for telescope control. To facilitate network access, Dave wrote a C program to convert the serial information to network. This program ran at the Kuiper and BOk telescopes on the guider computers. Around 2015 Mountain Ops decided it would be good to get this program off the guider computers and onto Mountain Ops computers. To do this, we used a Raspberrypi computer and rewrote the telcom program in python. You can find that source code [here](https://github.com/so-mops/legacy-py-telcom). A third telcom server was added to the Minnesota telescope to support dithering from the 2MASS camera. This source is very different as the Minnesota control system is very different. It can be found at [this github repository](https://github.com/so-mops/minn-telcom).

The Kuiper telescope control system was upgraded in 2016 to [TCSNG](https://github.com/so-mops/tcsng-unified). TCSNG has its own native network stack which should make the telcom system unnecessary. Unfortunately, the [communication protocol used by TCSNG](https://lavinia.as.arizona.edu/~tscopewiki/doku.php?id=public:tcs:ng_protocol) is slightly different that that [used by the legacy system](https://lavinia.as.arizona.edu/~tscopewiki/doku.php?id=tcs:legacy_tcs_socket_communction). Deep into the TCS upgrade at kuiper it was decided that it would be easier to create a modified version of telcom to convert between the old and new protocals rather than upgrade the software on subsystems that required telcom. Currently the two subsystems that require the modified telcom server at Kuiper are the SPOL instrument and the TCL based guider software.


Maintenance and Bugs
--------------------
Telcom has been fairly reliable especially considering the low cost of the hardware (raspberrypi). 


### Issue List
1. [Ocassionally telcom needs to be restarted to allow subystems to connect to its socket server.](https://github.com/so-mops/legacy-py-telcom/issues/1)
2. The rapsberrypi SD card needs to be replaced every few years. 
