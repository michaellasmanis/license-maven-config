# License Configuration

| Branch | Status |
| ------ | ------ |
|Master|[![Build Status](https://img.shields.io/circleci/project/github/michaellasmanis/license-maven-config/master.svg?style=flat)](https://circleci.com/gh/michaellasmanis/license-maven-config/tree/master) [![Maven Central](https://maven-badges.herokuapp.com/maven-central/com.lasmanis.maven/license-maven-config/badge.svg?style=flat)](https://maven-badges.herokuapp.com/maven-central/com.lasmanis.maven/license-maven-config)|

This project contains license templates for the [License Maven Plugin](http://code.mycila.com/license-maven-plugin/).

## Templates

* AllRightsReserved.txt : All rights reserved template

## Usage

Example configuration for the License Maven Plugin in the (parent) pom of the project:

    <project>
        <properties>
            <owner.name>Michael Lasmanis</owner.name>
            <owner.email>michael@lasmanis.com</owner.email>
        </properties>

        <build>
            <plugins>
                <plugin>
                    <groupId>com.mycila</groupId>
                    <artifactId>license-maven-plugin</artifactId>
                    <dependencies>
                        <dependency>
                            <groupId>com.lasmanis.maven</groupId>
                            <artifactId>license-maven-config</artifactId>
                            <version>0.0.1</version>
                        </dependency>
                    </dependencies>

                    <configuration>
                        <header>com/mycila/maven/plugin/license/templates/AllRightsReserved.txt</header>
                        <properties>
                            <owner>${owner.name}</owner>
                            <email>${owner.email}</email>
                        </properties>
                    </configuration>
                    <executions>
                        <execution>
                            <goals>
                                <goal>check</goal>
                            </goals>
                        </execution>
                    </executions>
                </plugin>
            </plugins>
         </build>
    </project>     
