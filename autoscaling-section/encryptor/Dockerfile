FROM gradle:jdk21 AS build
WORKDIR /app
COPY . /app


RUN chmod +x gradle
RUN ls -la
RUN pwd
RUN gradle build

FROM openjdk:21
COPY --from=build /app/build/libs/encryptor-0.0.1-SNAPSHOT.jar ./encryptor.jar
CMD [ "java", "-jar", "encryptor.jar" ]
