## How to create a custom connector apart from the Bonita Studio

Bonita offers the possibility to create au plug custom connectors, to allow you to connect with any external system you may need.  
A maven archetype is available on maven central to help you to bootstrap a connector project apart from the Bonita Studio. The source code of the archetype is available [here](https://github.com/bonitasoft/bonita-connector-archetype).

### Prerequisite

 1. Java must be installed: [https://adoptopenjdk.net/index.html](https://adoptopenjdk.net/index.html)
 2.  Maven must be installed: [https://maven.apache.org/install.html](https://maven.apache.org/install.html)
 3. Developing a connector apart from the Bonita Studio requires some software development skills. The  archetype offers the possibility to develop the connector in Java, Groovy or Kotlin. Make sure that you are comfortable with at least one of those three languages. 

### Create a Bonita connector project using the maven archetype

A maven archetype is a maven project templating toolkit (_[more details here](https://maven.apache.org/archetype/index.html)_). This archetype allows you to bootstrap a Bonita connector project on your file system. A Bonita connector project is a maven project. It can be built, and then imported into a Bonita Studio to be used.  

Before to create your project, you have to define: 

 - The **groupId** of your connector
     _used as a maven groupId_
 - The **artifactId** of your connector
    _used as a maven artifactId_
 - The **version** of your connector
    _used as a maven version_
 - The **name** of your connector
 - The targeted **Bonita version**: 
    A Bonita connector project depends on _org.bonitasoft.engine:bonita-common_. To avoid potential conflicts / errors at runtime, you should use the Bonita version of your runtime environment.
 - The **language** used in your project. Available values: 
     - java (_default_)
     - groovy
     - kotlin


To create your connector project, prompt a terminal and enter the following command: 
::: warning
**Warning:** Make sure that you are not executing the command from an existing maven project.
:::
```
mvn archetype:generate -DarchetypeGroupId=org.bonitasoft.archetypes -DarchetypeArtifactId=bonita-connector-archetype -DarchetypeVersion=1.0.0 -DgroupId=[YOUR GROUP ID] -DartifactId=[YOUR ARTIFACT ID] -Dversion=[YOUR VERSION] -DconnectorName=[YOUR CONNECTOR NAME] -DbonitaVersion=[TARGET BONITA VERSION] -Dlanguage=[YOUR LANGUAGE]
```
A folder name _[your artifact id]_ containing your project should be created. This connector project can already be built, imported and used in a process.