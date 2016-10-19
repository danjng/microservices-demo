FROM openjdk:8-jdk-alpine
RUN apk add --no-cache curl
ARG FINALNAME
EXPOSE 8001
HEALTHCHECK CMD curl --fail --user guest:guest123 http://localhost:8001/ || exit 1
ADD $FINALNAME.jar app.jar
RUN sh -c 'touch /app.jar'
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]