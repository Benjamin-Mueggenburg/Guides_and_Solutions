## Installing Protractor + Selenium
_This has been produced in accordance to GCI 2018 task: https://codein.withgoogle.com/tasks/6558667097767936_ for ScoreLab

### What is protractor?
[Protractor](https://www.protractortest.org) is a end-to-end test framework, in the form as a node.js program that's used in end-to-end (e2e) testing for [AngularJS](https://angularjs.org/) and [Angular](https://angular.io/) 

E2e testing is where the whole application is tested from start to finish. In webapps, there are several subsytems - external databases, interfaces, networks, even other applications that all commmunicate and interact with each other. E2E testing is making sure that these subsystems behave as intended, and that the data shared between them matains it's integrity.  

Not only does it test these subsystems; it also simulates real user scenearios, basically recreating how a real user would use the application. 

Negatives of e2e testing is that writing these tests is time consuming, costing companies much more money than, say, unit tests. E2e tests are expected to change and are slow to run, which is why on the [Google Testing Blog](https://testing.googleblog.com/2015/04/just-say-no-to-more-end-to-end-tests.html) it suggests 70% unit tests, 20% intergration tests and 10% e2e tests.

### Prerequisites
To get up an running with e2e (end to end) testing using protractor
