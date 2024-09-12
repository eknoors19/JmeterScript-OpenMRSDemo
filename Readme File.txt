Introduction -
--------------
 
This Jmeter Load Test Script is designed to load test OpenMRS demo application (https://demo.openmrs.org/openmrs/login.htm).
Jmeter 5.5 was used to create and execute this script. 
Total two scenarios have been developed in this framework namely - Register Patient and Search Patient.
This load test script generated both HTMl report and Aggregate report.

Thread Groups: 
/Register Patient:
	Steps performed in script
	- Launch Application
	- Login into Application 
	- While login, script selects random location for every iteration
	- Click Register Patient
	- Enter all the details:- FirstName, LastName, Gender, Address, PhoneNumber, Relationship etc
	- Confirm Registration
	- Logout
	- Save the created Patient Name in the csv file.

/Search Patient:
	Steps performed in script
	- Fetch created Patient Name from csv file to be used in below scenario.
	- Launch Application
	- Login into Application 
	- While login, script selects random location for every iteration
	- Click Find Patient
	- Enter FirstName, LastName in Search bar (details from csv file).
	- Click on Patient Record. 
	- Logout
	
CSV File Path set in the script: 
	- D:/NAGP2024/Jmeter/OpenMRS_Final/Enhanced Script/Search_Patient_First_and_LastNames.csv
	
JTL File path: 
	- D:\NAGP2024\Jmeter\Eknoor_3185683_JmeterAssignment\OpenMRS_Final\Enhanced Script\OpenMRS.jtl
	
Aggregate Report Path: 
	- D:\NAGP2024\Jmeter\Eknoor_3185683_JmeterAssignment\OpenMRS_Final\Aggregate Report\aggregate.csv
	
HTML Report Path: 
	- D:\NAGP2024\Jmeter\Eknoor_3185683_JmeterAssignment\OpenMRS_Final\HTML Report
	
Recorded jmx files Path: 
	- D:\NAGP2024\Jmeter\Eknoor_3185683_JmeterAssignment\OpenMRS_Final\Recording Files
	
Running the jmeter in non-GUI mode:
	- Both Scenarios:	
	jmeter -n -t "D:\Performanace\Performance Testing\JMeter\Final\Enhanced Script\OpenMRS.jmx" -l "D:\Performanace\Performance Testing\JMeter\Final\Enhanced Script\OpenMRS.jtl" -e -o "D:\Performanace\Performance Testing\JMeter\Final\HTML Report"
	
Things To Do before running script successfully: 
	- Please change path of CSV file before running script. Current path of csv file: D:/NAGP2024/Jmeter/OpenMRS_Final/Enhanced Script/Search_Patient_First_and_LastNames.csv
	- Before running script, please remove already placed FirstName, LastName from csv file. As, after sometime patient data gets deleted from application. Hence, Search scenario can fail as it searches old data. 
	- Please include below code in user.properties file before running this script: 
	  httpsampler.ignore_failed_embedded_resources=true