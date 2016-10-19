FROM openjdk:8-jdk-alpine
RUN apk add --no-cache curl
ARG FINALNAME
EXPOSE 8070
HEALTHCHECK CMD curl --fail http://localhost:8070/checkin/get/1 || exit 1
ADD $FINALNAME.jar app.jar
RUN sh -c 'touch /app.jar'
ENTRYPOINT ["java", "-Djava.security.egd=file:/dev/./urandom", "-jar", "/app.jar"]