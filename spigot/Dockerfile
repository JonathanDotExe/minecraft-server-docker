FROM openjdk:8-alpine
ARG MINECRAFT_VERSION=1.16.4
RUN apk add --no-cache wget && \
    apk add --no-cache git && \
    mkdir buildtools && \
    cd buildtools && \
    wget https://hub.spigotmc.org/jenkins/job/BuildTools/lastSuccessfulBuild/artifact/target/BuildTools.jar
RUN cd buildtools && \
    java -jar ./BuildTools.jar --rev ${MINECRAFT_VERSION}
RUN mkdir server
ENV MINECRFT_VERSION_ENV=$MINECRAFT_VERSION
CMD cd /server/data && \
    java -jar "../../buildtools/spigot-${MINECRFT_VERSION_ENV}.jar"