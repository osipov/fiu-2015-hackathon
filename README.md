#On this page you will find the getting started instructions and sample code for the FIU Cloud Hackathon which is a part of the [CEN4083 Introduction to Cloud Computing](http://visa.cis.fiu.edu/tiki/cen4083) course.

Before starting with any of the following instructions, ensure that you have IBM Bluemix account. You can register for one here: https://apps.admin.ibmcloud.com/manage/trial/bluemix.html

**What is IBM Bluemix?** IBM Bluemix is a open source based cloud computing platform for building, running, and managing applications. Bluemix is built on  [Cloud Foundry](http://cloudfoundry.org/about/index.html), a [Platform as a Service](http://thoughtsoncloud.com/2014/02/what-is-platform-as-a-service-paas/) technology with a broad community both contributing and supporting the project. With IBM Bluemix, developers can focus on writing code instead of worrying about how to setup hardware, install and upgrade operating systems, deploy and configure Cloud Foundry, or maintain a high level of availability for cloud infrastructure and applications. 

#Other Useful Services

* [Cloudant Document-oriented NoSQL Database](
https://github.com/IBM-Bluemix/fiu-2015-hackathon/blob/master/README.md#cloudant-document-oriented-nosql-database)
* [MySQL Relational Database](https://github.com/IBM-Bluemix/fiu-2015-hackathon#mysql-relational-database)
* [Sendgrid Email as a Service](https://github.com/IBM-Bluemix/fiu-2015-hackathon#sendgrid-email-as-a-service)
* [Twilio Telephony as a Service](https://github.com/IBM-Bluemix/fiu-2015-hackathon#twilio-telephony-as-a-service)
* [Internet of Things / Wearables](https://github.com/IBM-Bluemix/fiu-2015-hackathon#internet-of-things--wearables)
* [IBM Watson Question Answering for Travel](https://github.com/IBM-Bluemix/fiu-2015-hackathon#ibm-watson-question-answering-qa-for-travel)

##Cloudant Document-Oriented (NoSQL) Database

Cloudant is a JSON data store, a type of a NoSQL database that is an excellent fit for multi-structured data, unstructured data and fast-changing data models.

To try the sample Cloudant application, change directory to ```cloudant``` and and then deploy to Bluemix by executing the following commands:

```
cf login
cf create-service cloudantNoSQLDB Shared myCloudant
cf push
```

After the commands complete successfully, look for the console output specifying the application URL. It should look something like 

```
usage: 256M x 1 instances
urls: cloudant-random-word.mybluemix.net
```

Open your favorite browser using the URL ending with mybluemix.net (such as cloudant-random-word.mybluemix.net in the example above) from the console output to access the application. 

##MySQL Relational Database

PHP developer's default choice for a relational database, MySQL needs no introduction. With Bluemix, you can easily get a MySQL database with up to 10MB storage and up to 10 connections. 

To try the sample MySQL application, change directory to ```mysql``` and then deploy to Bluemix by executing the following commands:

```
cf login
cf create-service mysql 100 mySql
cf push
```

After the commands complete successfully, look for the console output specifying the application URL. It should look something like: 

```
usage: 256M x 1 instances
urls: mysql-random-word.mybluemix.net
```

Open your favorite browser using the URL ending with mybluemix.net (such as mysql-random-word.mybluemix.net in the example above) from the console output to access the application. 

##Sendgrid Email as a Service

Sendgrid is the world's largest email infrastructure as a service provider focused on deliverability, scalability, and reliability. 

To try the sample Sendgrid application, change directory to ```sendgrid``` and then deploy to Bluemix by executing the following commands:

```
cf login
cf create-service sendgrid free mySendgrid
cf push
```

After the commands complete successfully, look for the console output specifying the application URL. It should look something like: 

```
usage: 256M x 1 instances
urls: sendgrid-random-word.mybluemix.net
```

Next execute the following commands from your console, to specify custom to/from email addresses using Bluemix environment variables. 

```
cf set-env sendgrid TO_EMAIL bluemix@mailinator.com
cf set-env sendgrid FROM_EMAIL foo@bar.com
cf restage sendgrid
```

Open your favorite browser using the URL ending with mybluemix.net (such as sendgrid-random-word.mybluemix.net in the example above) from the console output to access the application. 

##Twilio Telephony as a Service

Twilio enables phones, VoIP, and messaging to be embedded into web, desktop, and mobile software. To try the Twilio on Bluemix, you will first need to register for a Twilio account (unless you already have one) using the following link https://www.twilio.com/try-twilio?promo=bluemix

You will also need a number that can receive text messages. This number must be verified with Twilio using the following link http://twilio.com/user/account/phone-numbers/verified

Once you are registered with Twilio and ready to try the sample Twilio application, change directory to ```twilio```  and execute the following commands from your console.

```
cf login https://api.ng.bluemix.net
cf push
```

After the command completes successfully, look for the console output specifying the application URL. It should look something like 

```
usage: 256M x 1 instances
urls: twilio-random-word.mybluemix.net
```

Take note of the URL ending with mybluemix.net (such as twilio-random-word.mybluemix.net in the example above) from the console output. You will need it later to access the application.

Twilio service must be bound to your application using the Bluemix UI. Login to Bluemix and using the Dashboard menu item, navigate to your application. Click on your application, click Add a service and choose Twilio from the catalog. On the right side bar, specify ```Twilio``` as the service name and enter the Twilio SID and token values as available from your Twilio dashboard.

A more detailed example of binding Twilio service to your application is available from https://twilio.com/blog/2014/02/twilio-and-ibm-codename-bluemix-nt.html

Next execute the following commands from your console, using your Twilio assigned phone number instead of the  ```<TWILIO_NUMBER>``` string and using a number where you want to send a text instead of ```<TEXT_NUMBER>```.

```
cf set-env twilio MY_TWILIO_NUMBER <TWILIO_NUMBER>
cf set-env twilio MY_DESTINATION_NUMBER <TEXT_NUMBER>
cf restage twilio
```

To test the application, open your favorite browser using the application URL you noted earlier, i.e the one ending with mybluemix.net.

##Internet of Things / Wearables

IBM built an Internet of Things (IoT) demo that collects heart rate data from users of a Mio Heart Rate Monitor ( http://www.heartratemonitorsusa.com/mio-alpha.html ), adds GPS-based location information from an iPhone, and persists the result in a Cloudant JSON datastore. 

The demo is deployed to Bluemix and is available from http://activetrack.mybluemix.net . On the demo website you can click on any of the trips on the left menubar, and then click play on the resulting popup to monitor location, speed, and heart rate of the user during the trip. 

The information used in the demo is available via an API. All of the trips shown on the left menu bar are available from using HTTP GET from http://hrtracker.mybluemix.net/api/trips/ . Once you know a specific tripId value from the trips API, you can pull up all of the data points from the trip using HTTP GET to a URL like http://hrtracker.mybluemix.net/api/trip/Amanda-1407354135195/data

The sample code provided as part of this repository illustrates how to use the REST API to retrieve data. To deploy and test out the sample code, change directory to ```iot``` and execute the following command:

```
cf login
cf push
```

After the command completes successfully, look for the console output specifying the application URL. It should look something like 

```
usage: 256M x 1 instances
urls: iot-random-word.mybluemix.net
```

Open your favorite browser using the URL ending with mybluemix.net (such as iot-random-word.mybluemix.net in the example above) from the console output to access the application. The page should render JSON with the demo data.

##IBM Watson Question Answering (QA) for Travel

The IBM Watson™ Question Answer (QA) for Travel service provides an API, referred to as the QAAPI, that enables you to add the power of the IBM Watson cognitive computing system to your application. With this service, you can connect to Watson, post questions, and receive responses that you can use in your application.

To try the sample Watson QA for Travel application, change directory to ```watson-qa``` and then deploy to Bluemix by executing the following commands:

```
cf login
cf create-service question_and_answer question_and_answer_free_plan myWatsonQa
cf push
```

After the commands complete successfully, look for the console output specifying the application URL. It should look something like 

```
usage: 256M x 1 instances
urls: watson-qa-random-word.mybluemix.net
```

Open your favorite browser using the URL ending with mybluemix.net (such as watson-qa-random-word.mybluemix.net in the example above) from the console output to access the application. 

The page lets you type in a question, like "What should I do in Prague" and ask Watson for document passages with answers. The web page in the index.html file uses Ajax requests to a PHP based service (implemented in ask.php) which in turn communicates with Watson.

## Frequently Asked Questions

0. **How does the Cloudant sample work?** The sample requires a Cloudant service to be bound to the application. Once the service is bound, the sample code in index.php pulls the credentials from the VCAP_SERVICES environment variable to connect to an application specific Cloudant instance. Once a user opens the application URL, the sample uses the Sag library to connect to your application's Cloudant instance, create a database and insert a JSON object in the database. If the insert completes successfully, the "hello world" message from the JSON object is retrieved from the database and echoed back to the browser.

0. **How does the Internet of Things / Wearables sample work?** The sample uses geocoded data available from the [Active Tracker](http://activetrack.mybluemix.net/) app which contains sample runs, walks, and car rides from IBM users of an iOS based heart rate monitor. Sample implementation in the index.php file relies on the REST API of the Active Tracker to pull geocoded data points that include heart rate, speed, and other data. After visualizing this data using [Active Tracker](http://activetrack.mybluemix.net/) you can try building leaderboards, statistical summaries, and other cool visualizations from this sample code.

0. **How does the MySQL sample work?** The sample requires a MySQL service to be bound to the application. Once the service is bound, the sample code in index.php pulls credentials along with connection information (e.g. hostname) from the VCAP_SERVICES environment variable to connect to an application specific MySQL instance. Once a user opens the application URL, the sample code connects to MySQL, creates a table, inserts a records, retrieves a record, echoes the record to the browser, and finally deletes the record from the database.

0. **How does the IBM Watson QA for Travel sample work?** The main entrypoint for the the sample is the ask.php file. Once the Watson QA service is bound to the application, authentication credentials and the connection URL for the Watson service are passed to ask.php via the VCAP_SERVICES environment variable. Once a user opens index.html in a browser and submits a question, ask.php handles the AJAX request from index.html, queries the Watson service REST API and returns the answers via the AJAX response. 

0. **How does the Sendgrid Email as a Service sample work?** The sample requires a Sendgrid service to be bound to the application. Once the service is bound, the sample code in index.php pulls the credentials from the VCAP_SERVICES environment variable to connect to an application specific Sendgrid instance. Once a user opens the application URL, the logic in index.php uses the credentials to connect to Sendgrid and send a "hello world" email. Next, index.php renders a simple status page with a hyperlink to check the temporary mailbox where the email is sent.

0. **How does the Twilio Telephony as a Service sample work?** The sample requires the developer to have a Twilio account and to validate 2 phone numbers with Twilio: one as a "text from" and another as a "text to". Twilio credentials must be entered when binding the service to the application using the Bluemix user interface. Once the service is bound, the sample code in index.php pulls the credentials from the VCAP_SERVICES environment variable to connect to an application specific Twilio instance. Once a user opens the application URL, the code in index.php composes a simple "hello world" text message and sends the text using Twilio. The status indicating whether the message was sent successfully is echoed back in the HTTP response.

0. **How do I pass environment variables to my application?** In Bluemix and Cloud Foundry you can use the command line tool to set application-specific environment variables. This is done using the ```cf set-env``` command or in your deployment manifest.yml file. More details on how to set the environment variables is available from http://docs.cloudfoundry.org/devguide/deploy-apps/manifest.html#env-block
You can also use the [email as a service sample](https://github.com/IBM-Bluemix/fiu-2015-hackathon#sendgrid-email-as-a-service) as an example.
