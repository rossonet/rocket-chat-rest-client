# rocket-chat-rest-client
Lightweight Java client for [Rocket.Chat](https://rocket.chat/)'s [REST API](https://rocket.chat/docs/developer-guides/rest-api) using [Unirest](http://unirest.io/java.html) and [Jackson](https://github.com/FasterXML/jackson-databind).

[![Build with Maven](https://github.com/rossonet/rocket-chat-rest-client/actions/workflows/build_with_maven.yml/badge.svg?branch=master)](https://github.com/rossonet/rocket-chat-rest-client/actions/workflows/build_with_maven.yml)

## Notes
* Requires Rocket.Chat v0.49.2 due to massive changes from Rocket.Chat, also v0.48 rewrote the REST API, see the [pull request #5140](https://github.com/RocketChat/Rocket.Chat/pull/5140) for details
* This api is still a work in progress, feel free to submit pull requests to add functionality
* Server url doesn't require `api/` anymore, but it can still be provided
* None of the results are cached, every time a method is called it goes out and gets it
* The method calls are sync and blocking
* Maven is configured to startup Rocket.Chat v.0.48-develop via docker therefore docker must be installed.

### JavaDoc
The JavaDoc is generated per build: https://ci.craftyn.com/job/rocket-chat-rest-client/javadoc/

### Maven
```xml
<repositories>
    <repository>
        <id>repo-snapshots</id>
        <url>https://repo.craftyn.com/repository/snapshots/</url>
    </repository>
</repositories>

<dependencies>
    <dependency>
        <groupId>com.github.baloise</groupId>
        <artifactId>rocket-chat-rest-client</artifactId>
        <version>0.1.2-SNAPSHOT</version>
    </dependency>
</dependencies>
```

### Compiling

The maven build needs [Docker](https://www.docker.com) for integration testing. Please install it for your platform before running and also make sure your user has permission to use the docker command (Linux, add your user to the docker group).

```
mvn clean install
```

To keep the docker containers running:

```
mvn -Ddocker.keepRunning clean install
```

