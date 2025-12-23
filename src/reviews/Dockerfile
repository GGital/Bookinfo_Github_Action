# MULTISTAGE Build
FROM gradle:8.1.1-jdk17-alpine AS builder

WORKDIR /opt/java/

COPY build.gradle gradle.properties* ./

RUN gradle dependencies --no-daemon 2>&1 | grep -v Warning || true
COPY src/ src/

COPY config/ config/

RUN gradle clean build --no-daemon -x test && \
    mkdir -p /opt/java/output && \
    cp build/libs/*.war /opt/java/output/reviews.war

# MULTISTAGE Run
FROM jetty:11-jdk17-alpine

COPY --from=builder /opt/java/output/reviews.war /var/lib/jetty/webapps/reviews.war

EXPOSE 9080

CMD ["java", "-jar", "/usr/local/jetty/start.jar"]