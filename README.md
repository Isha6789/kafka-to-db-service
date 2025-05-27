# 📦 Payload Consumer Application

## 📘 Overview

The Payload Consumer Application is a Spring Boot-based service designed to consume messages from a Kafka topic, process them, and store the data in a MySQL database. It includes robust error handling and unit tests to ensure reliability.

---

## 🚀 Features

- **Kafka Integration**: Consumes messages from a Kafka topic using Spring Kafka.
- **Message Parsing**: Parses JSON payloads into `MessageDto` objects.
- **Database Storage**: Stores processed messages in a MySQL database.
- **Error Handling**: Handles invalid payloads and logs errors for debugging.
- **Unit Testing**: Includes JUnit 5 tests for service methods.

---

## 📦 Prerequisites

- Java 17 or higher
- Maven 3.8+
- MySQL database
- Kafka server
- Docker (optional, for containerized deployment)

---

## ⚙️ Configuration

The application uses the `application.properties` file for configuration. Below are the key configurations:

### 🔧 Kafka & Database Configuration

```properties
# Kafka Properties
spring.kafka.consumer.bootstrap-servers=localhost:9092
spring.kafka.consumer.group-id=your_group_id
spring.kafka.consumer.auto-offset-reset=earliest
spring.kafka.consumer.enable-auto-commit=false
spring.kafka.consumer.key-deserializer=org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.consumer.value-deserializer=org.apache.kafka.common.serialization.StringDeserializer
spring.kafka.listener.poll-timeout=1000

# MySQL Properties
spring.datasource.url=jdbc:mysql://localhost:3306/production
spring.datasource.username=root
spring.datasource.password=your_password
spring.datasource.driver-class-name=com.mysql.cj.jdbc.Driver

# JPA Properties
spring.jpa.hibernate.ddl-auto=update
spring.jpa.show-sql=true
spring.jpa.properties.hibernate.format_sql=true



