# UI automation framework for Platform Services (SF + AWS)

For all Platform services modules where all test scenarios/steps are same - there is a need of singular automation framework which executes single script on both environments - Odin (Salesforce) & Zeus (AWS). Previously these were two different teams and were using different frameworks for ui automation.



## Framework Overview ##
 

***Feature file***:
Feature files are documents that contain Gherkin scripts & other relevant content. They are saved with the .feature extension. Path of feature file is ```src/test/java/Features```

***Step definition file***:
Step definition maps the Test Case Steps in the feature files to the code. An annotation followed by the pattern is used to link the Step Definition to all the matching Steps, and the code is what Cucumber will execute when it sees a Gherkin Step. Path of step definition file is ```src/test/java/StepDefinition```

***Runner file***:
We can run tests using a test runner file in Cucumber. The test runner file should contain the path of the feature file and step definition file that we want to execute. Location - ```src/test/java/Runner```

***Env properties file***:
Its a properties file where we are storing environment specific details like loginURL, HomePageURL, TestUserID.. etc. Path for *odin* is ```src/test/resources/config/odin``` and for *zeus* ```src/test/resources/config/zeus```

***Object repository***:
Its is a centralized storage of locators in the form of objects. Path for Odin is ```src/test/resources/config/odin``` and for zeus ```src/test/resources/config/zeus```

***Test class file***:
These are the java classes where we are actually writing the test methods. For each page/module we have separate class and one baseclass with name BasePage.java where we are initializing the selenium webdriver. You can find all test classes in ```src/main/java/com/simpplr/automation/page```

***Config file***:
Its a properties file where we are storing config flags like test environment, headless mode etc. Location - ```src/test/resources/config```

***Reports***:
Once execution is done - you can find detailed html reports in ```target/maven-cucumber-report/cucumber-html-reports```

For both Odin and Zeus all files are common except - Env property & Object repository file



## Defining the test environment ##
There are two ways to execute script on one particular environment

***Passing parameter using maven CLI***

 We can execute runner file in using maven command-line by passing test environment parameter.

For Odin ```mvn test -Drunner=Odin -DtestEnv=odin```


For Zeus ```mvn test -Drunner=Zeus -DtestEnv=zeus```

 
***Setting flag in config file***

Another way is adding value of key: execution_env in ```src/test/resources/config/config_flags.properties```


## Things to consider at the time of adding new module ##

If you want to add new feature/module in this framework - you may have to add .feature file, Step efinition in src/test/java and test class in ```src/main/java/com/simpplr/automation/page```.

Make sure you have key present in both project properties files -  ```src/test/resources/config/odin``` and ```src/test/resources/config/zeus```

---------------------------------------


