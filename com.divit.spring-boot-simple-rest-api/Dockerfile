FROM maven:3.8.5-openjdk-11 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

FROM openjdk:11
VOLUME /tmp
COPY /target/spring-boot-divit.jar app.jar
EXPOSE 8888
ENTRYPOINT ["java","-jar","/app.jar"]
