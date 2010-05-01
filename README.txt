Description
-----------
This library provides a Log4J Appender [1] that writes log events to the
MongoDB document oriented database [2].


Author
------
Peter Monks (pmonks@gmail.com)


Pre-requisites
--------------
JDK 1.6+
MongoDB Server v1.0+ (tested with 1.2.1, 1.4.x) (required for unit tests)
MongoDB Java Driver v1.0+ (tested with 1.2, 1.4)
Log4J 1.2+ (tested with 1.2.15 - note: won't work on earlier versions due to
            log4j API changes)


Installation / Configuration
----------------------------
1. Start a local MongoDB server running on the default port - this is required
   for the unit tests:
       mongod -dbpath ./mongodata

2. Build the JAR file using Maven2
       mvn clean package

3. Deploy the target/log4mongo-x.y.jar file, along with the Log4J and MongoDB
   Java Driver JARs, into the classpath of your Java application

4. Configure log4j as usual, referring to the log4j.properties.sample file for
   the specific configuration properties this appender supports


Todos
-----
* Clean up BSONification code - currently it's functional but skanky.
  Consider using daybreak for this [4].

* Add unit tests
  * test contents of logged events, not just document counts
  * authentication
  * exceptions (including nested exceptions) are stored correctly


References
----------
[1] http://logging.apache.org/log4j/1.2/index.html
[2] http://www.mongodb.org/
[3] http://github.com/mongodb/mongo-java-driver/downloads
[4] http://github.com/maxaf/daybreak