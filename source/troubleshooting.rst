Troubleshooting
===============

 .. image:: _static/dilbert_troubleshooting.png

 `Image credit-Dilbert`_

  .. _Image credit-Dilbert: http://dilbert.com/strip/2014-11-22

There are two ways to deal with this. We either say that you will never land in inexpliciable situations with our product or we give you a list of possible places where you may be stuck and subtly shift the blame on you. We will take the latter route.

Following are some issues that you may come across when using RobusTest. In case you do not find the issue you are facing on this page, log a support ticket by clicking `here <http://robustest.freshdesk.com>`_

 **I tried to click on Manual or Automation buttons but I get a message Unable to reach node server**

  This may happen because your computer is accessing RobusTest through a proxy server and the server is blocking WebSocket protocol

I ran my automation tests on the RobusTest Hub but I do not see anything in Live View

   A build URL is generated uniquely for every build and user. So, this could be because the build URL you are using to run your tests belongs to another person (and s/he is the one seeing an entry in his/her live view)

I am unable to see the test steps in the Live View for my device

   In case you are using RobusTest from behind a firewall, it is possible that the information related to test steps execution is being stopped. One check for this would be to run the following command

   telnet <RobusTest Installation Address> <port#>

   In case the connection is not successful, it is probable that the reason for not being able to view the test steps in Live View is the stopping of information by the firewall.
   
I am unable to access RobusTest
     Make sure your computer is connected to the network.
     Check if the server is running and reachable by executing a ping command on the RobusTest server
     
     ping <RobusTest server IP address>

     If the ping command is unsuccessful and you are unable to get a response from the server, it either means that the server is
     unreachable or that the server is down. Please check on this with your IT team
     If the ping command is successful and you are able to reach the server, then we check if the RobusTest server is running 
     successfully.
     
     Visit the RobusTest processes page and ensure that all processes are running as expected
     The URL for RobusTest processes page looks as below
     
     http://<robustest server url>:9001

     Make sure all the processes are in running state. 
     In case the URL above is not reachable, it means the RobusTest server is not running.
     Start the RobusTest application by running the following command on the system. You will need to login to the RobusTest server 
     using putty or similar tool.

      # cd /opt/code/RobusTest
      # screen -S FrontEnd
      # sudo su (enter the password when prompted)
      # ./StartServer.sh

   To find out the IP addresses of the deployment servers other such details, please contact your RobusTest administrator.
