FROM maven:3-jdk-8 as builder
RUN git clone https://github.com/srt7891/samplewebapp.git
RUN cd /gameoflifeondocker-master/game-of-life
WORKDIR /gameoflifeondocker-master/game-of-life
RUN mvn package


FROM tomcat:8
LABEL owner=none
EXPOSE 8080
COPY --from=builder /gameoflifeondocker-master/game-of-life/gameoflife-web/target/gameoflife.war /usr/local/tomcat/webapps/gameoflife.war
CMD ["catalina.sh", "run"]
