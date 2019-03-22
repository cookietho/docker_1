FROM alpine
RUN apk update && apk upgrade && apk add vim
ENTRYPOINT ["vim"]

# apk is the tool used to install, upgrade, or delete software on a running sytem.
# Dockerfiles should specify at least one of CMD or ENTRYPOINT commands. ENTRYPOINT should be defined when using the container as an executable.
# docker build -t ex00 .
# https://searchitoperations.techtarget.com/definition/Docker-image 
