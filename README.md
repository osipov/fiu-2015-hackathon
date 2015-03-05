#On this page you will find the getting started instructions and sample code for the [FIU Cloud Hackathon](http://visa.cis.fiu.edu/tiki/Cloud+Hackathon) conducted as a part of the [CEN4083 Introduction to Cloud Computing](http://visa.cis.fiu.edu/tiki/cen4083) course.

**THE PRESENTATION FROM THE INTRODUCTION TO BLUEMIX LECTURE WILL BE AVAILABLE BELOW** 

##Getting Started

Before starting with any of the following instructions, ensure that you have IBM Bluemix account. You can register for one here: https://apps.admin.ibmcloud.com/manage/trial/bluemix.html

Regardless of whether you choose to develop the hackathon project using Java or PHP, first download and install the latest release of the Cloud Foundry command line interface (CLI) for your operating system from https://github.com/cloudfoundry/cli/releases

All of the sample source code for this hackathon is available from public github.com repositories (repos). When you visit a repo webpage (e.g. https://github.com/osipov/bluemix-twilio-java-sample) there is a Download ZIP button that you can use to download the code without using git.

**OPTIONAL** [Git](https://en.wikipedia.org/wiki/Git_%28software%29) is often used for source code control in modern software development.  If you are planning a career in software development or systems administration, this project is a good opportunity for you to learn to use git. You can learn more about how to setup git in your development environment here: https://help.github.com/articles/set-up-git/

**If you are going to use Java**

Since you are going to be compiling your code locally ensure that you have both java and javac installed in your development environment. Your code will be running on Java 7 (v1.7) with JEE 6 libraries in Bluemix. You can download this version of the JDK from a variety of sources on the web, including from http://docs.oracle.com/javase/7/docs/webnotes/install/ . Remember that you need the JDK, not the JRE.

If have java and javac installed you can verify versions from the command line as follows

```
$ java -version

java version "1.7.0_65"
Java(TM) SE Runtime Environment (build 1.7.0_65-b17)
Java HotSpot(TM) 64-Bit Server VM (build 24.65-b04, mixed mode)

$ javac -version

javac 1.7.0_65
```

Download Apache Ant, a build tool for Java
http://mirrors.advancedhosters.com/apache//ant/binaries/apache-ant-1.9.4-bin.zip

Unzip the downloaded Ant zip package to someplace on your file system and ensure that the resulting apache-ant-1.9.4/bin directory is in your PATH variable

Confirm that you can run Ant from the command line as follows

```
$ ant -version

Apache Ant(TM) version 1.9.4 compiled on April 29 2014
```

**OPTIONAL** To simplify troubleshooting of Cloud Foundry deployments, it is recommended that you use Ant builds and deploy with Cloud Foundry CLI. However if you would like to use Eclipse to develop your Java application and push the application to Bluemix directly from Eclipse, start by checking that you have Eclipse for Java EE Developers (v4.4.1) installed. You can download this version of Eclipse for your operating system here: https://www.eclipse.org/downloads/packages/eclipse-ide-java-ee-developers/lunasr1 Open Eclipse and drag and drop the following URL to the Eclipse window http://marketplace.eclipse.org/marketplace-client-intro?mpc_install=1774120 This should prompt you to download IBM Eclipse Tools for Bluemix. Make sure that all of the features under IBM Eclipse Tools are checked, confirm, and complete the installation. To import sample code into Eclipse you can go to File > Import Existing Projects into Workspace > Archive File and point to one of the zip files you downloaded from the sample code repos. Documentation for deploying applications from Eclipse to Bluemix is available here: https://www.ng.bluemix.net/docs/#manageapps/eclipsetools/eclipsetools.html#eclipsetools

##What You Need to Know

**What is IBM Bluemix?** IBM Bluemix is an open source based cloud computing platform for building, running, and managing applications. Bluemix is built on  [Cloud Foundry](http://cloudfoundry.org/about/index.html), a [Platform as a Service](http://thoughtsoncloud.com/2014/02/what-is-platform-as-a-service-paas/) technology which has a broad community both contributing to and supporting the project. With IBM Bluemix, developers can focus on writing code instead of worrying about how to setup hardware, install and upgrade operating systems, deploy and configure Cloud Foundry, or maintain a high level of availability for cloud infrastructure and applications. More information about Bluemix is available from https://www.ng.bluemix.net/docs/#overview/overview.html#overview

**How do I run a Java Web Application on Bluemix?** There are three sample Java Web starter applications. The first is a very simple, Hello World style starter application which you can use as a template to add your code and push changes back to the Bluemix environment https://www.ng.bluemix.net/docs/#starters/liberty/index.html#liberty Second sample uses a relational database (IBM DB2) and another one uses a NoSQL, JSON document store (IBM Cloudant). When you run the sample application included with the Java DB2 boilerplate, a list is displayed. You can add, modify, and delete items from the list. Those items are saved to the back-end database. By default, this list contains instructions about how to use JPA or JDBC to access the database service that binds to the application. The default list also contains information about adding, deleting, and modifying the list items. https://www.ng.bluemix.net/docs/#starters/javaDB/index.html#javawebdatabase Third sample lets you run the Java Cloudant boilerplate, you get a favorites organizer for organizing the files on your computer in different categories. You can create, modify, and delete categories and upload files of different types in each of the categories. Cloudant NoSQL DB saves the data on the back end. The application creates a sample category by default. https://www.ng.bluemix.net/docs/#starters/java-cloudant/index.html#java-cloudant

**How do I run a PHP Web Application on Bluemix?** There is a very simple, Hello World style PHP starter application as a template so that you can add your code and push the changes back to the Bluemix environment. The PHP runtime environment is the container for this type of applications. More information is available here: https://www.ng.bluemix.net/docs/#starters/php/index.html#php

**Where can I get an overview of Watson services on IBM Bluemix** There is an [introductory video(https://www.youtube.com/watch?v=gSgYLy7ov9o) explaining what is IBM Watson and how it relates to IBM Bluemix. There is also a catalogue of Watson Services: https://www.ibm.com/smarterplanet/us/en/ibmwatson/developercloud/services-catalog.html

**How do I get help with Bluemix?** Start by searching the [question and answer forum](https://developer.ibm.com/answers/smartspace/bluemix/). If you can't find a good answer search the web. If that doesn't help, try posting your question to the forum. Tag your question with the word HACKATHON. Most questions are answered within 24 hours.

#Inspirational Examples

* [Your Celebrity Match with Watson Personality Modeling](https://github.com/osipov/fiu-2015-hackathon#your-celebrity-match-with-watson-personality-modeling)
* [Buying a smartphone with Watson Tradeoff Analytics](https://github.com/osipov/fiu-2015-hackathon#buying-a-smartphone-with-watson-tradeoff-analytics)
* [Build a collaborative encyclopedia of concept maps]()
* [Talent Hotspot](https://github.com/osipov/fiu-2015-hackathon#talent-hotspot-or-persona-fusion)
* [Remote Control of a Lego Robot](https://github.com/osipov/fiu-2015-hackathon#remote-control-of-a-lego-robot)

##Your Celebrity Match with Watson Personality Modeling
The [application](http://your-celebrity-match.mybluemix.net/) uses IBM Watson User Modeling and Twitter to find the celebrities that are similar to your personality. Twitter is being use to get the tweets for a given handler, the text from those tweets is send to User Modeling, who analyze the text and reply with a personality profile. That profile is compared to celebrity profiles to find the most similar. The source code for the application is available here: https://github.com/watson-developer-cloud/yourcelebritymatch

##Buying a smartphone with Watson Tradeoff Analytics
This [application](http://tradeoff-analytics-demo.mybluemix.net/) built with the Watson Tradeoff Analytics service helps find the best available options for you when buying a smartphone. The Tradeoff Analytics service is designed to help users make better decisions under multiple conflicting goals. The service processes a range of alternatives (e.g. different cell phone models) and objectives (e.g. maximize screen size) and helps identify the alternatives that fit in the [Pareto efficient frontier](http://en.wikipedia.org/wiki/Pareto_efficiency#Overview). The service also generates a multidimensional visualization to help guide the selection of an optimal alternative.

##Build a collaborative encyclopedia of concept maps
The [Concept Maps application](http://conceptmaps.info/) is a collaborative repository for easily sharing and searching high-level knowledge to gain insight quickly into a topic and related information. The site is the realization of a vision that we, as lean innovators, had for a space where knowledge can be: 1) collaboratively and effectively organized, presented, and optimized for fast consumption and navigation; 2) indexed to be searchable both locally and by crawling engines; 3) annotated for easy sharing on social media and other, more-direct communication formats. There is more about how to write the app here: http://www.ibm.com/developerworks/cloud/library/cl-conceptmaps-app/index.html 

##Talent Hotspot or Persona Fusion
Talent Hotspot is a web application that allows you to search for candidates from a pool of applicants based on how closely they resemble one of your current employees. Talent Hotspot uses Watson's User Modeling API service to analyze a potential candidate's personality based on their answers to a questionnaire. The application can issue queries such as, "Find me a Developer like Craig Smith". Then search through all possible candidate and return a ranked list of candidates sorted by highest-to-lowest percentage of personality resemblance. From here, searches can be refined by including technical skills. "Find me a Developer like Craig Smith, and knows Java, C and Python". The source code for the application is available here: https://github.com/jsloyer/talent-manager-complete


##Remote Control of a Lego Robot
If you have access to a LEGO Mindstorms robot you might be interested in trying out [this application](https://developer.ibm.com/bluemix/2015/01/19/remote-control-ev3-robot-via-ibm-bluemix-iot/). The LEGO kit comes with some motors and touch, color and infrared sensors. The kit also contains a remote control leveraging the infrared sensor and you can drive the robot from iOS and Android devices via Bluetooth. There is [a video](https://www.youtube.com/watch?v=o-LgOk9OJMw) showing how the robot can be connected to the Bluemix Internet of Things service to enable remote control of the robot from a Bluemix application.

#Other Useful Services

* [Cloudant Document-oriented NoSQL Database](https://github.com/osipov/fiu-2015-hackathon#cloudant-document-oriented-nosql-database)
* [DB2 Relational Database](https://github.com/osipov/fiu-2015-hackathon#db2-relational-database)
* [Sendgrid Email as a Service](https://github.com/osipov/fiu-2015-hackathon#sendgrid-email-as-a-service)
* [Twilio Telephony as a Service](https://github.com/osipov/fiu-2015-hackathon#twilio-telephony-as-a-service)

##Cloudant Document-Oriented (NoSQL) Database

Cloudant is a JSON data store, a type of a NoSQL database that is an excellent fit for multi-structured data, unstructured data and fast-changing data models.

**If you are going to use Java**
Deploy the Java Cloudant boilerplate described here: https://www.ng.bluemix.net/docs/#starters/java-cloudant/index.html#java-cloudant

**If you are going to use PHP**
Use the instructions available here: https://github.com/osipov/bluemix-cloudant-php-sample

##Sendgrid Email as a Service

**If you are going to use Java**
Use the instructions available here: https://github.com/osipov/bluemix-sendgrid-java-sample

**If you are going to use PHP**
Use the instructions available here: https://github.com/osipov/bluemix-sendgrid-php-sample

##Twilio Telephony as a Service

Twilio enables phones, VoIP, and messaging to be embedded into web, desktop, and mobile software. To try the Twilio on Bluemix, you will first need to register for a Twilio account (unless you already have one) using the following link https://www.twilio.com/try-twilio?promo=bluemix

You will also need a number that can receive text messages. This number must be verified with Twilio using the following link http://twilio.com/user/account/phone-numbers/verified

**If you are going to use Java**
Follow the example shown during the first lecture on Bluemix.

**If you are going to use PHP**
Use the instructions available here: https://github.com/osipov/bluemix-twilio-php-sample

##DB2 Relational Database

**If you are going to use Java**
Deploy the Java Cloudant boilerplate described here: https://www.ng.bluemix.net/docs/#starters/javaDB/index.html#javawebdatabase

**If you are going to use PHP**
DB2 is not supported with the PHP buildpack, but you can use MySQL instead. Details on how to do that are available here: https://github.com/osipov/bluemix-mysql-php-sample

## Frequently Asked Questions

0. **How does the Cloudant sample work?** The sample requires a Cloudant service to be bound to the application. Once the service is bound, the sample code in index.php pulls the credentials from the VCAP_SERVICES environment variable to connect to an application specific Cloudant instance. Once a user opens the application URL, the sample uses the Sag library to connect to your application's Cloudant instance, create a database and insert a JSON object in the database. If the insert completes successfully, the "hello world" message from the JSON object is retrieved from the database and echoed back to the browser.

0. **How does the MySQL sample work?** The sample requires a MySQL service to be bound to the application. Once the service is bound, the sample code in index.php pulls credentials along with connection information (e.g. hostname) from the VCAP_SERVICES environment variable to connect to an application specific MySQL instance. Once a user opens the application URL, the sample code connects to MySQL, creates a table, inserts a records, retrieves a record, echoes the record to the browser, and finally deletes the record from the database.

0. **How does the Sendgrid Email as a Service sample work?** The sample requires a Sendgrid service to be bound to the application. Once the service is bound, the sample code in index.php pulls the credentials from the VCAP_SERVICES environment variable to connect to an application specific Sendgrid instance. Once a user opens the application URL, the logic in index.php uses the credentials to connect to Sendgrid and send a "hello world" email. Next, index.php renders a simple status page with a hyperlink to check the temporary mailbox where the email is sent.

0. **How does the Twilio Telephony as a Service sample work?** The sample requires the developer to have a Twilio account and to validate 2 phone numbers with Twilio: one as a "text from" and another as a "text to". Twilio credentials must be entered when binding the service to the application using the Bluemix user interface. Once the service is bound, the sample code in index.php pulls the credentials from the VCAP_SERVICES environment variable to connect to an application specific Twilio instance. Once a user opens the application URL, the code in index.php composes a simple "hello world" text message and sends the text using Twilio. The status indicating whether the message was sent successfully is echoed back in the HTTP response.

0. **How do I pass environment variables to my application?** In Bluemix and Cloud Foundry you can use the command line tool to set application-specific environment variables. This is done using the ```cf set-env``` command or in your deployment manifest.yml file. More details on how to set the environment variables is available from http://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html#env-block
You can also use the [email as a service sample](https://github.com/osipov/fiu-2015-hackathon#sendgrid-email-as-a-service) as an example.
