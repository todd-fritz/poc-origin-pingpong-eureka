FROM java:7
MAINTAINER todd-fritz
# Update the image with the latest packages (recommended)
#
#
VOLUME /tmp
ADD poc-origin-pingpong-eureka-1.0.0-SNAPSHOT.jar /app.jar
RUN bash -c 'touch /app.jar'
ENV EUREKA_HOST poc-eureka
ENV EUREKA_PORT 8761
EXPOSE 8761
ENTRYPOINT ["java","-Djava.security.egd=file:/dev/./urandom","-jar","/app.jar"]