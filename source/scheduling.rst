Scheduling your tests
=====================

You can use RobusTest to schedule your automation tests.
To schedule your tests you should follow the steps below

1. Create a test suite - Create a test suite by adding all the test cases that you wish to be part of the test run
2. Create a test run - Run the test suite created above by selecting the devices that you wish to run it on
3. Get the "Run ID" - For the run that was just created, a unique Run ID is generated. To get the Run ID, click on the Reports icon for the run. In the Reports page, copy the last part of the URL. e.g. if the Reports link is 

http://mobile.robustest.com/#/project/57d0f2e4aca33b21f5724cd7/report/58498732aca33b11ca655660

the Run ID is 58498732aca33b11ca655660
4. Customize the scheduling API - Scheduling API looks like

http://<RobusTest URL>/api/1/run/<Run ID>?updateFromTestSuite=true&build=latest

e.g if you Run ID is 58498732aca33b11ca655660 and your RobusTest URL is http://192.168.1.1:8081, then your scheduling API will look like

http://192.168.1.1:8081/api/1/run/58498732aca33b11ca655660?updateFromTestSuite=true&build=latest

Every time above API is called, the test suite will be run on the devices selected on the latest build of the project.

5. Schedule run API - Once you have customized the run API, you need to add it as a cron job on your test run server.