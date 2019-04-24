FROM alpine/git
WORKDIR /app
RUN git clone https://github.com/sriman-biarca/hello-world.git

FROM maven:3.5-jdk-8-alpine
WORKDIR /app
COPY --from=0 /app/hello-world /app 
RUN mvn package 

FROM openjdk:8-jre-alpine
WORKDIR /app
RUN ls -la
COPY --from=1 /app/target/hellow-world-0.0.1.jar /app 
EXPOSE 8080
ENTRYPOINT ["sh", "-c"]
CMD ["java -jar hellow-world-0.0.1.jar"] 
##sample-test
