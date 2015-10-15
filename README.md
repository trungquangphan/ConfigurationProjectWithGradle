# ConfigurationProjectWithGradle
SimpleConfigurationProjectWithGradle

This project make the process of configuration loose coupling with the development.
It will help the system administrator switches the enviroment easily, quickly and safe.
  Follow the below steps to complete the journey:
1. Put all properties for each enviroment in one place.
For the convinient, put all data in one place,like config.groovy file. 
If you have too many property, you can split it into serveral groovy file.

2. Declare all properties will be used by your application and surround them by @ character
Normally, most of web application in java (Spring MVC,...) read information via property files. 
Let's create a property file, such as application.property, it will contain all nessessary information for building and running.
Then ,you need to do is surround the property name with the ‘@’ character.

3. Use ConfigSlurper to create and load environment configurations
ConfigSlurper is a utility class within Groovy for writing properties file like scripts for performing configuration.
In this sample, it will load all data from config.groovy file, then fill into a map of properties.
Depend on your purpose (build a jar file, or copy property files to source folder,...) you need to insert value for all property of application.properties file by using filer method.  

4. Tell Gradle which environment to build

Set env property for the destination environment. For example on the command line:
gradle build -Penv=prod

