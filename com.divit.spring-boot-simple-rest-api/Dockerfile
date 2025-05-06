# Etapa de build
FROM maven:3.8.5-openjdk-11 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -DskipTests

# Etapa de execução
FROM openjdk:11-jre-slim
VOLUME /tmp
COPY --from=build /app/target/spring-boot-divit.jar app.jar
EXPOSE 8888
ENTRYPOINT ["java", "-jar", "app.jar"]
