# cgl-dxo-qa-api
cgl-dxo-qa-api


CAN SOAP UI Automation Framework::
=====================================
The SOAP UI Automation Framework is created for REST APIs only. It should not be used for testing - SOAP Based Web Services.

When you open the Prooject in you will find -
1. API Endpoints (Based pon these API endpoints, we have created test cases)
2. AutomationRun Test Suite: This test suite contains the code for automating the REST API testing & generating the HTML Report, Log Files and other  necessary artifacts.
	The code is written in Groovy & Java targeting JRE 1.7 or higher. The automation code written in this test suite takes the execution control at runtime and runs the manual test suites/test cases one after the other and generates the HTML Test Report & Execution Log files. By default, the HTML Report is stored on the Desktop of the current user.

	->To change the HTML Report Path, you can set the project-level property - "HTMLReportPath" either in SoapUI GUI or via CLI.
	->To change the HTML Report File Title, you can set the project-level property - "HTMLReportTitle" in SoapUI GUI or via CLI.
	->To change the Environment for the API testing, you can set the project-level property - "Environment" in  SoapUI GUI or via CLI.


3. API_RegressionSuite Test Suite: This test suite contains all the manual/functional test cases based on the API endpoints which are already added in the project.



=> Steps to apply this SoapUI Framework to other projects:
------------------------------------------------------------
1. Open the CAN SOAP UI Project in SoapUI
2. Delete the "API_RegressionSuite" and the other manual test suites/test cases
3. Delete all the endpoints which are not required for your project.
4. "Save as" the project




=>Steps to setup/run SoapUI automation project via CLI command on MacOS/Linux:

SOAP UI 5.2.1:
---------------
1. Install SoapUI on your Mac/Linux machine
2. Run following CLI command-

sh /Applications/SoapUI-5.2.1.app/Contents/Resources/app/bin/testrunner.sh -sAutomationRun /Users/ketdeshp/Documents/SOAPUI/CAN_Rest_API_Project.xml



=> If you face any NetSocket Exception or network connectivity issue on SoapUI Version 5.2.1 or older version due to firewall policy of the organization, please do the following-

Steps to change the TLS socket connection issue in SOAP UI 5.2.1:
-----------------------------------------------------------------

1) vim /Applications/SoapUI-5.2.1.app/Contents/vmoptions.txt

2) press "i" to enter insert mode

3) Add the following line to the vmoptions.txt file:
-Dsoapui.https.protocols=TLSv1.2

4) press "esc" button & type :wq to save and exit






