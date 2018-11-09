## Installing Protractor + Selenium
_This has been produced in accordance to GCI 2018 task: https://codein.withgoogle.com/tasks/6558667097767936_ for ScoreLab

### What is protractor?
[Protractor](https://www.protractortest.org) is a end-to-end test framework, in the form as a node.js program that's used in end-to-end (e2e) testing for [AngularJS](https://angularjs.org/) and [Angular](https://angular.io/) 

E2e testing is where the whole application is tested from start to finish. In webapps, there are several subsytems - external databases, interfaces, networks, even other applications that all commmunicate and interact with each other. E2E testing is making sure that these subsystems behave as intended, and that the data shared between them matains it's integrity.  

Not only does it test these subsystems; it also simulates real user scenearios, basically recreating how a real user would use the application. 

Negatives of e2e testing is that writing these tests is time consuming - costing companies more money than, say, unit tests. Furthermore e2e tests are expected to change and are slow to run, which is why on the [Google Testing Blog](https://testing.googleblog.com/2015/04/just-say-no-to-more-end-to-end-tests.html) it suggests 70% unit tests, 20% intergration tests and 10% e2e tests.

### Prerequisites
To get up and running install:
+ [**NodeJS**](https://nodejs.org/en/download/) - download and run installer for your OS

### Setup Nodejs project
You may skip this step if you have already done so.

Open your command prompt in a new directory created for your project:<br/>
Run `npm init` and answer the prompts. This should create a `package.json` file.

### Install Protractor
Now for the interesting part - installing protractor.

Using a command prompt in your project directory containing `package.json`<br/>
Run `npm install -g protractor` 

Test the installation with `protractor --version`. If it returns with the version number, the installation was successful. 

### Introduction to Selenium
For protractor to work, it needs a webdriver. A webdriver specifies the API that can be used to interact with browsers. This means human actions such as moving the mouse, pressing keys, clicking on buttons, can be automated and done so through code functions specified in API. 

Protractor uses the [Selenium Remote Control (RC)](https://www.seleniumhq.org/projects/remote-control/) server, which is written in Java, that accepts commands sent over HTTP for the browser. 

### Installation and Running of Selenium server
#### Prerequisites
+ [Java Development Kit (JDK)](http://www.oracle.com/technetwork/java/javase/downloads/index.html) - Run installer. Selenium Server requires it to be installed. Use `java -version` to test whether installation was successful.

#### Installation of Selenium server
Installing protractor, provides two command line tools - `protractor` and `webdriver-manager`. `webdriver-manager` is a helper tool that makes it easy to get an instance of the Selenium server running.

Download necessary binaries:
`webdriver-manager update`

#### Run Selenium RC Server
Start the Selenium  Server with:
`webdriver-manager start`





