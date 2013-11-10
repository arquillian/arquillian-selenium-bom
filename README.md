Selenium BOM (Bill of Materials)
================================

This project intends to improve Selenium dependency management by specifyng POM managing dependency versions for all Selenium artifacts.

Usage
=====

Add following snippet to your project's POM:

    <properties>
        <version.selenium>2.36.0</version.selenium>
    </properties>

    <dependencyManagement>
        <dependencies>
            ...
            <dependency>
                <groupId>org.jboss.arquillian.selenium</groupId>
                <artifactId>selenium-bom</artifactId>
                <version>${version.selenium}</version>
                <type>pom</type>
                <scope>import</scope>
            </dependency>
            ...
        </dependencies>
    </dependencyManagement>

Place the `selenium-bom` import declaration above any other import which manages Selenium dependencies in order to get dependencies managed correctly.

For more information about dependency management, see [Introduction to Dependency Management](http://maven.apache.org/guides/introduction/introduction-to-dependency-mechanism.html).

Installing
==========

In order to install new version of Selenium dependency, change `${version.selenium}` version to the one you would like to install and run

    mvn install

Deploying
=========

In order to install new version to configured repository (`distrubutionManagement` section), change `${version.selenium}` and then run:

    mvn deploy
