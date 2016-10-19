FROM openjdk:8-jdk-alpine
RUN apk add --no-cache curl
ARG FINALNAME
EXPOSE 8090
HEALTHCHECK CMD curl --fail -H "Content-Type: application/json" -X POST -d '{}' http://localhost:8090/search/get || exit 1
ADD $FINALNAME.jar app.jar
RUN sh -c 'touch /app.jar'
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]