FROM eclipse-temurin:17-alpine


RUN addgroup -g 1028 devopsc && \
    adduser -D -G devopsc admin

VOLUME /tmp  

ARG JAR_FILE
ARG ARG DB_PASSWORD
COPY ${JAR_FILE} app.jar

ENV DB_PASSWORD=DB_PASSWORD

RUN chown -R admin:devopsc /tmp

USER admin

EXPOSE 8080

ENTRYPOINT [ "java", "-jar", "/app.jar" ]