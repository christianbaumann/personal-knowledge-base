# Introducing Maven: A Build Tool for Today's Java Developers
Author: Balaji Varanasi

https://www.amazon.de/gp/product/1484254090

* **Archetype**
  * Pre-defined project templates to generate new projects
  * Create project from archetype: `mvn archetype:create-from -project`

**CoC** "Conventions over Configuration" (or "Coding by Convention")  

**Transitive dependency** Dependency declaredin the POM, that itself has further dependencies. (Others: Direct dependency)  

**Dependency scope**
* **compile**
  * available in class path, in all project phases (biold, test, run)
  * default scope
* **provided**
  * available during build and test
  * don't get bundled
* **runtime**
  * not available during build
  * get bundled
* **test**
  * available during test phase
* **system**
  * similar to provided scope
  * get bundled
* **import**
  * for pom file dependencies only  

**Show dependencies** (as tree) `mvn dependency:tree`  

**Maven properties**
  * referenced in pom.xml
  * notation `${property_name}`
  * two types: implicit, user defined
    * implicit
      * available to every Maven project
      * POM properties via `project.`-prefix, eg `${project.artifactId}`
      * settings.xml: `${settings.}`
      * environment variables: `env.`, eg `${env.PATH}`
    * custom
      * via `<properties>` element eg 
        ```
        <properties>
          <junit.version>4.12</junit.version>
        </properties>
        ```
        → `${junit.version}`

* build process requires several steps and tasks
* _goals_ to represent granular tasks
* goals are packaged in plugins
* `mvn plugin_identifier:goal_identifier`, eg
  * `mvn compiler:compile`, or
  * `mvn clean:clean`
  
  → compiler and clean are plugins!
* goals are granular and perform one task
* help plugin lists available goals in a given plugin, eg `mvn help:describe -Dplugin=compiler`
* plugins and their behaviour are configured in the `<plugins>` section of the pom.xml
* multile goals need to be executed in order

  → Maven simplifies this via lifecycle and phase abstractions, so that build-related operations can be done with a handfule of commands
* build lifecycle consists of a series of stages (= phases) executed in same order
* build in lifecycles
  * **default** compile, package and deploy
  * **clean** deletes temp files and generated artifacts from `/target`
  * **site** generates documentation and site

* **lifecycle**
  * abstract concept
  * cannot be executed directly, instead you
  * execute one or more phases
  * phases prior to requested phase are also executed
  * number of tasks executed per phase
  * each phase is associated with zero or more goals
  * phase delegates tasks to its associated tasks (p. 59, gif 5-1)
  
**Site lifecycle** to generate project documentation
* `mvn site` → `/target/site`
* Javadoc reports
  * add `maven-javadoc-plugin` to pom.xml
  * → `/target/site/apidocs`
* Unit Test reports
  * add `maven-surefire-report-plugin` to pom.xml
      * → `/target/SurefireReports`: xml + txt
      * → `/target/surefire-reports`: html