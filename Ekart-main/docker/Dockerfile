FROM openjdk:17-jdk
ENV APP_HOME /usr/src/app
WORKDIR $APP_HOME
#RUN echo "Asia/Colombo" | tee /etc/timezone
#RUN dpkg-reconfigure --frontend noninteractive tzdata
RUN ln -snf /usr/share/zoneinfo/Asia/Colombo /etc/localtime && echo "Asia/Colombo" > /etc/timezone
COPY target/shopping-cart-0.0.1-SNAPSHOT.jar $APP_HOME/app.jar
#ADD application.properties /backend/application.properties
WORKDIR $APP_HOME
EXPOSE 8070
ENTRYPOINT ["java","-jar","-Dlogging.level.org.springframework.core.env=DEBUG"," shopping-cart-0.0.1-SNAPSHOT.jar ","--server.port=8070"]
