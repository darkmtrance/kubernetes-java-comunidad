FROM openjdk:17.0-jdk-slim-buster as dev

WORKDIR /work

COPY mvnw /work/mvnw
COPY .mvn /work/.mvn
COPY pom.xml /work/pom.xml

RUN ./mvnw dependency:go-offline

COPY . /work/
RUN ./mvnw install -DskipTests

RUN chmod +x /work/target/demoPod-0.0.1-SNAPSHOT.jar

ENTRYPOINT ["java","-jar","/work/target/demoPod-0.0.1-SNAPSHOT.jar"]
