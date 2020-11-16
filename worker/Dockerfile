FROM maven:3.5-jdk-8-alpine as builder

WORKDIR /worker

COPY . .

RUN mvn dependency:resolve

RUN mvn package

FROM openjdk:8-jre-alpine

COPY --from=0 /worker/target/worker-jar-with-dependencies.jar .