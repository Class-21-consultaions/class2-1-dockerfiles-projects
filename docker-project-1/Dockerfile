FROM   ubuntu 
RUN    echo "class21 project 1"
CMD    date 
ENTRYPOINT [ "echo", "hello" ]

#git docker to clone a git repository

FROM  alpine/git 
WORKDIR /app
RUN      git clone   https://github.com/Lion-Technology-Solutions/liontech-online-library-web-app.git

#maven

FROM   maven:3.5-jdk-8-alpine as build 
WORKDIR /app 
COPY  --from=repo /app/liontech-online-library-web-app   /app/
RUN mvn test 
RUN mvn install 
RUN  mvn clean package 