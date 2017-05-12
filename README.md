## Log42j mock for Elasticsearch 5.x [![Travis](https://img.shields.io/travis/ctron/de.dentrassi.elasticsearch.log4j2-mock.svg)](https://travis-ci.org/ctron/de.dentrassi.elasticsearch.log4j2-mock) [![Maven Central](https://img.shields.io/maven-central/v/de.dentrassi.elasticsearch/log4j2-mock.svg)](https://search.maven.org/#search%7Cgav%7C1%7Cg%3A%22de.dentrassi.elasticsearch%22%20AND%20a%3A%22log4j2-mock%22)

This is a mock implementation of `org.apache.logging.log4j:log4j-core`, just enough to
satisfy Elasticsearch 5.x to work with other logging frameworks such as SLF4J.

Elasticsearch 5.x has a hard dependency on log4j 2, but not only on the API, also on
the internal classes. This means that if you want to use the embedded node, you are forced
to use log4j 2 as well, which may not always be possible.

This implementation provides enough of log4j 2 to trick Elasticsearch into working and not
tinkering around with log4j internals. All logging which is original going over log4j2, still
can be redirected to SLF4J and will work. What will not work is the re-configuration of the
logging configuration which Elasticsearch enforces, this is simply ignored.

### Maven coordinates

```xml
<dependency>
    <groupId>de.dentrassi.elasticsearch</groupId>
    <artifactId>log4j2-mock</artifactId>
    <version><!-- version --></version>
</dependency>
```