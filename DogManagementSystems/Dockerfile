# Build Stage
FROM maven:3.8.2-jdk-11 AS build
WORKDIR /app
COPY . .
RUN mvn clean package -Pprod -DskipTests

# Runtime Stage
FROM openjdk:11-jdk-slim
WORKDIR /app
COPY --from=build /app/target/DogManagementSystem-0.0.1-SNAPSHOT.jar DogManagementSystem.jar
CMD ["java", "-jar", "DogManagementSystem.jar"]
