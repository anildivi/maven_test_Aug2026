# HelloWorld Maven - JDK 21

A simple Java Maven project configured for JDK 21 and Maven 3.9.x.

## Requirements

- JDK 21
- Maven 3.9.x
- Git

Verify:

```bash
java -version
javac -version
mvn -version
```

Maven should report Java 21 as the Java runtime.

## Build without Jenkins

```bash
mvn clean package
```

Run the executable JAR:

```bash
java -jar target/hello-world-maven-1.0.0.jar
```

## Expected output

```text
The current local time is: <current-time>
Hello world!
```

## Project structure

```text
HelloWorldMaven/
├── pom.xml
├── README.md
├── .gitignore
├── src/
│   └── main/
│       └── java/
│           └── hello/
│               ├── HelloWorld.java
│               └── Greeter.java
└── Jenkinsfile
```

## Jenkins

The included Jenkinsfile runs:

1. Checkout
2. Verify Java and Maven
3. Clean
4. Compile
5. Test
6. Package
7. Archive the JAR

### Jenkins prerequisites

- Jenkins agent with JDK 21
- Maven 3.9.x installed
- Git available
- Jenkins Pipeline support

Update the tool names in the Jenkinsfile if your Jenkins installations use different names.

## GitHub

```bash
git init
git add .
git commit -m "Initial commit - JDK 21 Maven 3.9 project"
git branch -M main
git remote add origin <YOUR_GITHUB_REPOSITORY_URL>
git push -u origin main
```
