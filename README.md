# 04-flink-base

This repository is a Flink learning and practice project covering the core APIs, SQL/Table API, state management, windows, CDC integration, and real-world user behavior analysis examples. It includes multiple modules for different Java/Scala versions and Flink versions.

## Project overview

The project is organized as a Maven multi-module aggregation project:

- `flink-base-java-13`: Java examples built around Flink 1.13
- `flink-base-java-20`: Java examples built around Flink 1.20, including more practical business cases
- `flink-base-scala-10`: Scala examples targeting Flink 1.10
- `flink-base-scala-15`: Scala examples targeting Flink 1.15

The modules are designed for learning and demos rather than production deployment.

## Included topics

The code covers common Flink concepts and patterns such as:

- Word count and basic stream processing
- Data sources and sinks
- Transformations and keyed operations
- Windows and watermarks
- ProcessFunction and side outputs
- State and checkpoint related examples
- Table API and SQL
- Kafka, JDBC, Redis, Elasticsearch and HBase integrations
- MySQL/TiDB CDC examples
- User behavior analysis cases:
  - hot items
  - network traffic analysis
  - marketing analysis
  - login detection
  - order timeout detection

## Repository structure

```text
04-flink-base/
├── pom.xml
├── flink-base-java-13/
│   ├── pom.xml
│   └── src/main/java/
├── flink-base-java-20/
│   ├── pom.xml
│   └── src/main/java/
├── flink-base-scala-10/
│   ├── pom.xml
│   └── src/main/scala/
├── flink-base-scala-15/
│   ├── pom.xml
│   └── src/main/scala/
└── README.md
```

## Prerequisites

- JDK 8 or newer
- Maven 3.6+
- A local or remote Flink-compatible environment for running streaming jobs
- Optional services for connector demos:
  - Kafka
  - MySQL / TiDB
  - Redis
  - Elasticsearch
  - HBase

## Build

From the project root:

```bash
mvn clean package
```

To build a single module:

```bash
cd flink-base-java-20
mvn clean package
```

## Run examples

Most examples are Java/Scala `main` classes. You can run them from your IDE or package the module and launch the target class with the generated classpath.

Example:

```bash
cd flink-base-java-20
mvn clean package
```

Then run the desired class in IntelliJ IDEA / Eclipse / VS Code Java extension, or use a command similar to:

```bash
java -cp target/flink-base-java-20-1.0-SNAPSHOT.jar:<dependency-classpath> com.itbys._01_flink_base_java._01_word_count.DataStreamTest
```

The exact runtime command depends on the sample and the build output.

## Important notes

- This project is mainly educational and demo-oriented.
- Some examples require external systems such as Kafka or MySQL to be running.
- Connector versions in the POM files are mixed across Flink versions and may need adjustment depending on your environment.
- For production-grade deployments, it is recommended to align all Flink, connector, and JVM versions consistently.

## Typical example entry points

A few representative classes:

- `flink-base-java-20/src/main/java/com/itbys/_01_flink_base_java/_01_word_count/DataStreamTest.java`
- `flink-base-java-20/src/main/java/com/itbys/_01_flink_base_java/_09_cdc/MysqlCdcApi.java`
- `flink-base-java-20/src/main/java/com/itbys/_02_user_behaviors_analysis/_01_HotItemsAnalysis/HotItemsAnalysis.java`
- `flink-base-scala-10/src/main/scala/com/atguigu/flink_first_look/dsApi/DataStreamWC.scala`

## License

This project is provided for learning and demonstration purposes. Please check the repository license if one is added later.

## Related learning path

If you are studying Flink, a practical order is:

1. Basic source / transform / sink
2. Window and watermark
3. State and checkpoint
4. ProcessFunction
5. Table API and SQL
6. CDC and connectors
7. Real business analytics cases

This repository is a good companion for those steps.
