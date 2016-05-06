# Instructions to Install IBM MQ 8.0.0.3 client jars to WSO2 ESB.

## Prerequisites

1) Install Java and Set JAVA_HOME environment variable (Prerequisites for Maven)

2) Install Apache Maven 3.X and Set MAVEN_HOME and M2 environment variables

3) IBM MQ 8.0.0.3 Java libraries (jars)

## Build Instructions

1) Copy following jars from `<IBM MQ 8.0.0.4 installation Directory>\java\lib` directory to `lib` folder.
	* com.ibm.mq.allclient.jar
	* fscontext.jar
	* jms.jar
	* providerutil.jar

2) Build project using Apache Maven with following command line command `mvn clean install`

	
## Installing IBM MQ Client jars to WSO2 ESB 4.8.x - 4.9.x

1) Stop WSO2 ESB server, if it is already running.

2) (If present) Remove old IBM MQ client jars from `<ESB_Home>\repository\components\dropins` and `<ESB_Home>\repository\components\lib`

3) Copy `target\wmq-client-8.0.0.4.jar` to `<ESB_Home>\repository\components\dropins`

4) Copy [jta.jar](http://central.maven.org/maven2/javax/transaction/jta/1.1/jta-1.1.jar) to `<ESB_Home>\repository\components\lib`

5) Remove `javax.jms,\` line from `<ESB_Home>\repository\conf\etc\launch.ini`

6) [Important] Regenerate `.bindings` file with following property. `Provider Version : 8`

7) Replace old `.bindings` file with new `.bindings` file.

8) Start ESB server.
