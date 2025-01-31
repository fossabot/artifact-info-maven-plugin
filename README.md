# artifact-info-maven-plugin
[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FBBE78%2Fartifact-info-maven-plugin.svg?type=shield)](https://app.fossa.com/projects/git%2Bgithub.com%2FBBE78%2Fartifact-info-maven-plugin?ref=badge_shield)

Artifact Info Maven Plugin automatically generates your Maven project information from your `pom.xml` into a Java class, usable into your Java application.

## Usage Example
The following pluging usage:
``` xml
<?xml version="1.0" encoding="UTF-8"?>
<project xmlns="http://maven.apache.org/POM/4.0.0"
         xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"
         xsi:schemaLocation="http://maven.apache.org/POM/4.0.0 http://maven.apache.org/xsd/maven-4.0.0.xsd">

  <modelVersion>4.0.0</modelVersion>

  <groupId>com.mycompany.myproject</groupId>
  <artifactId>myapp</artifactId>
  <version>1.2.3-SNAPSHOT</version>

  <name>My Application</name>
  <description>The description of my Application...</description>

  <build>
    <plugins>
      <plugin>
        <groupId>io.github.bbe78</groupId>
        <artifactId>artifact-info-maven-plugin</artifactId>
        <version>1.0</version>
        <executions>
          <execution>
            <id>default-generate</id>
            <phase>generate-sources</phase>
            <goals>
              <goal>generate</goal>
            </goals>
          </execution>
        </executions>
      </plugin>
    </plugins>
  </build>

</project>
```

will generate the following class:
```java
package com.mycompany.myproject;

import java.io.PrintStream;


/**
 * Generated by Artifact Info Maven Plugin v1.0
 * More information on https://github.com/BBE78/artifact-info-maven-plugin
 */
public final class ArtifactInfo {

    /** The project group ID. */
    private static final String GROUP_ID = "com.mycompany.myproject";

    /** The project artifact ID. */
    private static final String ARTIFACT_ID = "myapp";

    /** The project version. */
    private static final String VERSION = "1.2.3-SNAPSHOT";

    /** The project name. */
    private static final String NAME = "My Application";

    /** The project description. */
    private static final String DESCRIPTION = "The description of my Application...";

    /** The user name that built the project. */
    private static final String BUILT_BY = "<username>";

    /** The project build date. */
    private static final String BUILD_DATE = "2017-02-43 22:22:49 UTC";

    /** The host name where the project was built. */
    private static final String BUILD_HOST = "<hostname>";


    /**
     * Returns the project groupId.
     * Could not be <code>null</code>.
     *
     * @return the project groupId.
     */
    public static String getGroupId() {

        return GROUP_ID;
    }


    /**
     * Returns the project artifactId.
     * Could not be <code>null</code>.
     *
     * @return the project artifactId.
     */
    public static String getArtifactId() {

        return ARTIFACT_ID;
    }


    /**
     * Returns the project version.
     * Could not be <code>null</code>.
     *
     * @return the project version.
     */
    public static String getVersion() {

        return VERSION;
    }


    /**
     * Returns the project name.
     * Could not be <code>null</code> but could be empty.
     *
     * @return the project name.
     */
    public static String getName() {

        return NAME;
    }


    /**
     * Returns the project description.
     * Could not be <code>null</code> but could be empty.
     *
     * @return the project description.
     */
    public static String getDescription() {

        return DESCRIPTION;
    }


    /**
     * Returns the user name that built the project.
     * Could be <code>null</code> or empty.
     *
     * @return the user name that built the project.
     */
    public static String getBuiltBy() {

        return BUILT_BY;
    }


    /**
     * Returns the project build date as String in GMT timezone.
     * Could not be <code>null</code>.
     *
     * @return the project build date.
     */
    public static String getBuildDate() {

        return BUILD_DATE;
    }


    /**
     * Returns the host name where the project was built.
     * Could not be <code>null</code> but could be <code>unknown</code>.
     *
     * @return the host name where the project was built.
     */
    public static String getBuildHost() {

        return BUILD_HOST;
    }


    /**
     * Returns the project full name, composed of the project name and project version.
     * Could not be <code>null</code>.
     *
     * @return the project full name.
     */
    public static String getFullName() {

        return getName() + " [v" + getVersion() + "]";
    }


    /**
     * Main entry of this class: display in the standard out the properties.
     *
     * @param args
     *      the program arguments, not used.
     */
    public static void main(String[] args) {

        displayProperties(System.out);
    }


    /**
     * Display the properties on the specified PrintStream.
     *
     * @param out
     *      the PrintStream where properties will be displayed.
     */
    public static void displayProperties(final PrintStream out) {

        out.println(getFullName());
        out.println("\t- groupId    : " + getGroupId());
        out.println("\t- artifactId : " + getArtifactId());
        out.println("\t- version    : " + getVersion());
        out.println("\t- name       : " + getName());
        out.println("\t- description: " + getDescription());
        out.println("\t- built by   : " + getBuiltBy());
        out.println("\t- build date : " + getBuildDate());
        out.println("\t- build host : " + getBuildHost());
    }

}
```

## Dependencies
The generated class file is free of any dependency.

## Issues
Please report any issues or enhancements in [GitHub Issues Sytem](https://github.com/BBE78/artifact-info-maven-plugin/issues).

## License
Artifact Info Maven Plugin is delivered under the Apache License v2.


[![FOSSA Status](https://app.fossa.com/api/projects/git%2Bgithub.com%2FBBE78%2Fartifact-info-maven-plugin.svg?type=large)](https://app.fossa.com/projects/git%2Bgithub.com%2FBBE78%2Fartifact-info-maven-plugin?ref=badge_large)