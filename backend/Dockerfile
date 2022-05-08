FROM openjdk:8-jdk-alpine
VOLUME /tmp
VOLUME /app
VOLUME /app/properties
ENV SPRING_CONFIG_LOCATION="/app/properties/application.properties"
WORKDIR /app
ARG JAVA_OPTS
ENV JAVA_OPTS=$JAVA_OPTS
COPY src/main/resources/application.properties /app/properties/application.properties
COPY target/backend-0.0.1-SNAPSHOT.jar /app/backend.jar
EXPOSE 8080
ENTRYPOINT [ "sh", "-c", "java $JAVA_OPTS -Djava.security.egd=file:/dev/./urandom -jar backend.jar --spring.config.location=$SPRING_CONFIG_LOCATION " ]