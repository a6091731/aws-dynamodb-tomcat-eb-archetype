# aws-dynamodb-session-tomcat-wrapper-archetype
A maven archetype that will generate a new war enabled for aws dynamodb session persistence a la aws-dynamodb-session-tomcat

# Usage
1.  You will need to first clean, compile and install this archetype. At the moment it is not hosted in maven central:

  ```
  mvn clean install
  ```
2.  Generate your wrapped war project:

  ```
  mvn archetype:generate \
  -DarchetypeGroupId=com.rapid7.aws \
  -DarchetypeArtifactId=aws-dynamodb-session-tomcat-wrapper-archetype \
  -DarchetypeVersion=1.0-SNAPSHOT \
  -DgroupId=<YOURGROUPID> \
  -DartifactId=<YOURARTIFACTID> \
  -Dversion=1.0-SNAPSHOT
  ```

3.  Edit ``pom.xml`` inside the generated project and update the maven coordinates of your war:

  ```
  ...
                              <artifactItems>
                                  <artifactItem>
                                      <groupId>[wrapped war groupId]</groupId>
                                      <artifactId>[wrapped war artifactId]</artifactId>
                                      <version>[wrapped war version]</version>
                                      <type>war</type>
                                      <outputDirectory>${project.build.directory}/war-contents</outputDirectory>
                                  </artifactItem>
                              </artifactItems>
  ...
  ```
