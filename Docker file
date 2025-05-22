# Stage 1: Build
FROM maven:3.9.4-eclipse-temurin-17 AS builder
WORKDIR /app
COPY . .
RUN mvn clean package

# Stage 2: Runtime
FROM tomcat:9.0.85
COPY --from=builder /app/target/WebAppCal-1.3.5.war /usr/local/tomcat/webapps/calculator.war
