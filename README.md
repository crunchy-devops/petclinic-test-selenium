# Set up selenium Tests
Check the pom.xml definition and the code source of the class PetclinicTest.java 
**Attention** The IP address of the test version of the website is hardcoded that shouldn't 
be done in the real CI/CD environment.  
  
## Create a Jenkins Job
### Define 
if the plugin Log Parser is not present  
Go to manage-Jenkins -> Manage plugins -> Tab available -> Filter Log Parser   
Check and install without restart   
  
Go New Item, Name petclinic-selenium, select Maven-project  
Hit Ok  
Source Management   
Git  https://github.com/<your_repo>/petclinic-test-selenium.git  
Build  
Root POM: pom.xml  
Goals and options: test   
  
### Post-build Actions   
Select Console ouptut (build log) parsing  
Tick Mark build Failed on Error  
Tick Use project rule  
Path to rule file in workspace :  parserules   
parserules file contains a regex for checking if there is an error 

