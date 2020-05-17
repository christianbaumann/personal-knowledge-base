# A Practical Guide to Testing in DevOps
Author: [Katrina Clokie](https://twitter.com/katrinaclokie)

https://leanpub.com/testingindevops

##### page 5
* set of practices
* collaboration & communication
* automating software delivery
* culture & environment
* rapid/ frequent/ reliable

-> not mentioning tools at all

* CD != DevOps
* CD: software is always production ready
* CD focusses on technical practices

##### page 7
Testing can be done everywhere in the DevOps cycle

##### pages 10-16
Test Strategy Retrospective

##### pages 17-18
Agile Testing Assessment

##### pages 21-39
Skipped. Might be relevant in big orgs, but not where I am right now

##### pages 43, 45
build environments on demand

##### page 45
test the pipeline

##### page 52
Bug Bash

##### page 56
Testing in production: Decisions can be deferred, but it needs preparation

##### page 58
* Monitoring info to drive future testing
* monitors and alerts need to be tested

##### page 62
* Test logging: bugs should be determinable from the logs
* production logs can show hidden issues
* ["Why and how to test logging" by Matthew Skelton](https://blog.matthewskelton.net/2016/10/31/why-and-how-to-test-logging-infoq-article/)

##### pages 66-71
skipped (AB testing, beta testing)

##### page 72
"Sufficiently advanced monitoring is indistinguishable from Testing"

##### page 73
* Don´t wait for user to interact with a feature, run automated tests to generate events in production.
* Passive and active validation

##### pages 77-81
skipped (Exposure control)

##### pages 85-88
skipped (Installing Apache)

##### page 93
* reduce number of test environments in the development process
* code should pass straight from development environment to the production environment

##### pages 94-95
* Infrastructure Testing
* Tools: Test Kitchen, [ServerSpec](https://serverspec.org/)

##### pages 96-98
* Destructive Testing
* Tools: [Netflix Simian Army](https://github.com/Netflix/SimianArmy)
