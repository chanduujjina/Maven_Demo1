# Maven_Demo1

## Introduction to Maven
-  What is Maven?

-  Why do we need Maven?

- Traditional vs Maven project structure

## Maven Basics
  - How Maven works (Build Lifecycle)

  - Maven coordinates (groupId, artifactId, version)
  - pom.xml structure overview
    
## Maven Directory Structure
    - src/main/java

    - src/test/java

    - target/ folder

 ## Core Concepts

 - Dependencies and Repositories

- Transitive dependencies

- Maven Central Repository

- Dependency scope (compile, test, provided, runtime)

 ## Maven Phases and Lifecycle
  - validate, compile, test, package, install, deploy

  - Custom lifecycle overview (optional)

## Plugins and Goals
 - Compiler plugin

- Surefire plugin (for unit testing)

- Shade plugin (for creating fat JARs)

- Exec plugin (to run Java classes)

## Common Commands
 - mvn clean

- mvn compile

- mvn package

- mvn install

- mvn dependency:tree

🏗️ Commonly Used Maven Archetypes

| Archetype ID                                     | Description                                          |
| ------------------------------------------------ | ---------------------------------------------------- |
| `maven-archetype-quickstart`                     | ✅ Basic Java project (Main class + test class)       |
| `maven-archetype-webapp`                         | 🌐 Java Web app with `web.xml` (Servlet/JSP)         |
| `maven-archetype-j2ee-simple`                    | EE app base with `EJB`, WAR modules                  |
| `maven-archetype-site-simple`                    | 📄 Generates Maven project documentation site        |
| `maven-archetype-archetype`                      | Used to create your own custom archetype             |
| `maven-archetype-plugin`                         | For building Maven plugins                           |
| `maven-archetype-portlet`                        | Liferay/JSR portlet-based project                    |
| `maven-archetype-mojo`                           | To write your own Maven mojo (plugin goals)          |
| `org.springframework.boot:spring-boot-archetype` | 🧪 Spring Boot application starter (less common now) |

```bash
mvn archetype:generate -DgroupId=com.demo -DartifactId=my-app -DarchetypeArtifactId=maven-archetype-quickstart -DinteractiveMode=false
```
# Explaination of the above Command in tabular Format
| Attribute                                          | Meaning                                                                                         |
| -------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| `mvn`                                              | Invokes Maven                                                                                   |
| `archetype:generate`                               | Tells Maven to run the **archetype plugin** to generate a new project                           |
| `-DgroupId=com.demo`                               | **Group ID** — Java package-style name that uniquely identifies your project (like a namespace) |
| `-DartifactId=my-app`                              | **Artifact ID** — name of the project/folder and the `.jar` name                                |
| `-DarchetypeArtifactId=maven-archetype-quickstart` | Specifies which **project template** to use (in this case, a basic Java app template)           |
| `-DinteractiveMode=false`                          | Runs without asking questions in the terminal (non-interactive)                                 |

# This generates a folder with:

```bash
src/
 └─ main/java
 └─ test/java
pom.xml
```

📂 Structure Overview

| Folder/File    | Purpose                       |
| -------------- | ----------------------------- |
| `pom.xml`      | Maven configuration file      |
| `App.java`     | Main class generated          |
| `AppTest.java` | Sample test class using JUnit |


✅ Maven Core Commands & Goals
| Command               | Type        | Purpose                                                                |
| --------------------- | ----------- | ---------------------------------------------------------------------- |
| `mvn clean`           | Lifecycle   | Deletes the `target/` directory (removes previous build artifacts)     |
| `mvn compile`         | Lifecycle   | Compiles the Java source code (from `src/main/java`)                   |
| `mvn test`            | Lifecycle   | Runs unit tests using test framework (e.g., JUnit)                     |
| `mvn package`         | Lifecycle   | Packages compiled code into `.jar` or `.war` (inside `target/`)        |
| `mvn install`         | Lifecycle   | Installs the packaged `.jar` into **local Maven repo** (`~/.m2`)       |
| `mvn dependency:tree` | Plugin Goal | Shows the **complete tree of dependencies**, including transitive ones |

🔍 Details of Each
# mvn clean
🧹 Deletes the target/ folder to ensure a fresh build .Use it before compile or package to avoid stale files.
```bash
mvn clean
```
# mvn compile
🛠️ Compiles your .java files in src/main/java
 - Output: .class files in target/classes
```bash
mvn compile
```
# mvn package
📦 Compiles + tests + creates .jar or .war file Based on <packaging> in pom.xml:
- <packaging>jar</packaging> → JAR

- <packaging>war</packaging> → WAR

```bash
mvn package

```
 
 # mvn install
 📥 Installs your built artifact to local repository (~/.m2/repository) .Other projects on the same machine can use this version.

 ```bash
mvn install
```

# mvn dependency:tree
🌳 Shows how your dependencies are connected (direct + transitive) Very useful to:
 - Detect version conflicts
 - See what's bringing an unwanted dependency

```bash
mvn dependency:tree
```
🧠 Real-World Analogy

| Phase            | Analogy                              |
| ---------------- | ------------------------------------ |
| clean            | Wipe old ingredients off the table   |
| compile          | Chop and prepare raw materials       |
| package          | Cook and pack the meal               |
| install          | Put meal into your home fridge       |
| dependency\:tree | See how all ingredients were sourced |

