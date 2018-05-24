# maven-getting-started

## [https://maven.apache.org/guides/getting-started/maven-in-five-minutes.html](quick-started)

## [https://maven.apache.org/guides/getting-started/index.html](getting-started)

### setting checked
mvn --version

### goal
validate: `validate the project is correct and all necessary information is available`

compile: `compile the source code of the project`

test: `test the compiled source code using a suitable unit testing framework. These tests should not require the code be packaged or deployed`

package: `take the compiled code and package it in its distributable format, such as a JAR.`

integration-test: `process and deploy the package if necessary into an environment where integration tests can be run`

verify: `run any checks to verify the package is valid and meets quality criteria`

install: `install the package into the local repository, for use as a dependency in other projects locally`

deploy

clean: `cleans up artifacts created by prior builds`

site: `generates site documentation for this project`

### create project
mvn archetype:generate

mvn archetype:generate -DinteractiveMode=false -DarchetypeArtifactId=maven-archetype-quickstart \
-DgroupId={project-packaging} -DartifactId={project-name}

### compile
    mvn compile
    mvn test-compile

### test
    mvn test

### jar package
    mvn package

### batch
    mvn install

### create reference
    mvn site

### clear
    mvn clean

### change java compile version
```
<plugin>
  <groupId>org.apache.maven.plugins</groupId>
  <artifactId>maven-compiler-plugin</artifactId>
  <configuration>
    <source>1.8</source>
    <target>1.8</target>
    <encoding>UTF-8</encoding>
  </configuration>
</plugin>
```

### running
    java -cp target/my-app-1.0-SNAPSHOT.jar com.mycompany.app.App

### etc
```
mvn archetype:generate -DgroupId=com.mycompany.app -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
```
mvn archetype:generate \
    -DarchetypeGroupId=org.apache.maven.archetypes \
    -DarchetypeArtifactId=maven-archetype-webapp \
    -DgroupId=com.mycompany.app \
    -DartifactId=my-webapp
```
- maven-archetype-quickstart
- spring-boot-sample-simple-archetype
- spring-boot-sample-data-jpa-archetype
- spring-boot-sample-actuator-log4j-archetype
```
mvn archetype:generate -DinteractiveMode=false -DarchetypeArtifactId=maven-archetype-quickstart \
-DgroupId={project-packaging} -DartifactId={project-name}

mvn archetype:generate -DinteractiveMode=false \
-DarchetypeGroupId=org.springframework.boot -DarchetypeArtifactId={spring-archetype} \
-DgroupId={project-packaging} -DartifactId={project-name}

mvn archetype:generate -DinteractiveMode=false \
-DarchetypeGroupId=org.springframework.boot -DarchetypeArtifactId=spring-boot-sample-simple-archetype \
-DgroupId={project-packaging} -DartifactId={project-name}
```
### create mvnw
```
mvn -N io.takari:maven:wrapper -Dmaven=3.3.3
```
