RobusTest Hub
=============
 .. image:: _static/buildURL.png

With RobusTest you can also execute your Appium test cases created outside of RobusTest on the devices connected to the platform. Doing so requires a few simple changes to your Appium execution script. More specifically these changes need to be made to the desired capabilities that are specified before starting an Appium Server. Following are the values that need to be provided/updated in the desired capabilities object


1. app - set the value for this URL to the build URL for the specific build that you wish to test on. You will get the build URL from the project page and upon selecting a particular build
2. device - set this value to the name of the device that you wish to run on. The list of names of devices available for use can be obtained from the device dialog available when you click on Record button on the project page

Make sure you change the Appium URL from your local Appium server, which usually looks like http://localhost:4723/wd/hub.  After the change, your RobusTest Hub URL will look like http://192.168.2.34:3142/wd/hub. Actual IP address and port number may vary based on your RobusTest installation.
