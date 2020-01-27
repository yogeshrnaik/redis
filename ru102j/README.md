# redisolar

How to start the redisolar application
---

1. Run `mvn package` to build your application
2. Start application with `java -jar target/redisolar-1.0.jar server config.yml`
3. To check that your application is running enter url `http://[HOST]:8081`. If you're
running on localhost, HOST will be "localhost".

Tests
---

To run all tests:

```
mvn test
```

To run a specific test:

```
mvn test -Dtest=JedisBasicsTest
```

Health Check
---

To see your applications health enter url `http://localhost:8084/healthcheck`





# Getting Started
Redis University offers hosted, private virtual labs for every student. The goal is to make your learning experience simple and pleasurable. However, that may not be the best solution for every student, so below we list a couple of other options for you to run the labs for this course. In general, you have three options:

- Hosted Virtual Lab
- Your own Docker environment
- Your own Redis/Java environment

If you run into any issues and need some assistance, please post a message on the discussion forums. Staff and Teaching Assistants are there to help.

## Option 1: Virtual Lab
If you are using the provided Virtual Lab, simply click "Launch Your Lab" in sections entitled Launch Your Lab.

Please note: After 21 days, the labs are automatically decommissioned and any data, code and files are removed. Please store these elsewhere if you want to preserve any of this.

Once your lab is running, see the next section, Running the Sample Application, for instructions on how to compile the code, run the test suite, and start the front-end app.

## Option 2: Run the Lab in Your Docker Environment
If you have access to a Docker environment, we've created a Docker image.  This contains an IDE, a Redis Server, source code, and sample data. Follow these instructions to use the image.

1. Run the Docker container
```
$ docker run --rm --name redis-lab-102j -p:8888:8888 -p:8081:8081 redisuniversity/ru102j-lab
```

2. Point your browser to

http://localhost:8888/entry.html

Once your lab is running, see the next section, Running the Sample Application, for instructions on how to compile the code, run the test suite, and start the front-end app.

## Option 3: Use your own Redis/Java environment
If you want to use your own infrastructure to run the Labs for this course, please follow these instructions

1. Download and install Redis. The minimum version is 5.0.3 for this course.

2. Confirm you have Java 8 or higher and Maven installed:

1. Check your Java version:

```
redisu$ java -version
openjdk version "1.8.0_212"
OpenJDK Runtime Environment (IcedTea 3.12.0) (Alpine 8.212.04-r0)
OpenJDK 64-Bit Server VM (build 25.212-b04, mixed mode)
```

2. Confirm Maven is installed:

```
redisu$ mvn --version
Apache Maven 3.5.2 (138edd61fd100ec658bfa2d307c43b76940a5d7d; 2017-10-18T07:58:13Z)
Maven home: /usr/share/java/maven-3
Java version: 1.8.0_212, vendor: IcedTea
Java home: /usr/lib/jvm/java-1.8-openjdk/jre
Default locale: en_US, platform encoding: UTF-8
OS name: "linux", version: "4.9.125-linuxkit", arch: "amd64", family: "unix"
```

3. Download the Java project:

[RU102J Java Project Source Code](https://assets-university.redislabs.com/ru102j/ru102j-project.zip)

Once your lab is running, see the next section, Running the Sample Application,for instructions on how to compile the code, run the test suite, and start the front-end app.

## Windows 10
A number of students have had success running the course of Windows 10 (using the April 2018 release). This is not something we have tried ourselves. Please note that there is no active port of Redis for Windows, and versions you may find are very out of date (e.g. 3.2.1).

Students have been successful by using the Windows subsystem for Linux, and install the Linux version of Redis. See the following articles

https://docs.microsoft.com/en-us/windows/wsl/install-win10 

# Running the Sample Application
Make sure you can complete the following steps before continuing. This will allow you to participate in the programming challenges that appear throughout the course.

You can run all of the following commands from the project base directory (the one that contains the file "pom.xml").

## Building the Project
```
$ mvn package
```

Running the Test Suite
```
$ mvn test
```
Running an individual test case:
```
$ mvn test -Dtest=HelloTest
```

## Loading the Sample Data
The sample application includes a data loader. You should run this after completing each programming challenge. Often, you'll be writing code that inserts data into the application. Running the data loader will ensure that this data is always up to date.

```
$ java -jar target/redisolar-1.0.jar load
```

## Running the Sample Application
You'll also want to be able to run the sample application. From the command line, run the following:
```
$ java -jar target/redisolar-1.0.jar server config.yml
```

Now, if you're running this on your local machine, or using Docker, you can then navigate to http://localhost:8081 to see the app.

If you're using the virtual labs, you'll need to take two steps:

1. Open a new browser window.

2. Copy the URL from the original window hosting your virtual lab. Then modify the URL as follows:

Replace the 8888 at the beginning of the URL with 8081.
Remove the "/entry.html" path.
So, for example, if your virtual lab URL is

https://8888-9999999.university.redislabs.com/entry.html
you'll need to change it to

https://8081-9999999.university.redislabs.com/
to hit the app in the new browser window.
