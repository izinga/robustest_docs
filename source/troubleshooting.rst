Troubleshooting
===============

 .. image:: _static/dilbert_troubleshooting.png

 `Image credit-Dilbert`_

  .. _Image credit-Dilbert: http://dilbert.com/strip/2014-11-22

There are two ways to deal with this. We either say that you will never land in inexpliciable situations with our product or we give you a list of possible places where you may be stuck and subtly shift the blame on you. We will take the latter route.

 * I ran my automation tests on the RobusTest Hub but I do not see anything in Live View

   A build URL is generated uniquely for every build and user. So, this could be because the build URL you are using to run your tests belongs to another person (and s/he is the one seeing an entry in his/her live view)

 * I am unable to see the test steps in the Live View for my device

   In case you are using RobusTest from behind a firewall, it is possible that the information related to test steps execution is being stopped. One check for this would be to run the following command

   telnet <RobusTest Installation Address> <port#>

   In case the connection is not successful, it is probable that the reason for not being able to view the test steps in Live View is the stopping of information by the firewall.

   To find out the installation address and port#, please contact your RobusTest administrator.