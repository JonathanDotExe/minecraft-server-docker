FROM openjdk:8-alpine
RUN apk add --no-cache wget && \
    apk add --no-cache git && \
    mkdir buildtools && \
    cd buildtools && \
    wget https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar
RUN cd buildtools && \
    java -jar ./BuildTools.jar --rev 1.16.5
RUN mkdir server && \
    cp /buildtools/spigot-1.16.5.jar /server && \
    cd server
CMD cd /server/data && \
    java -jar ../spigot-1.16.5.jar
