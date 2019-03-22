FROM debian
RUN apt-get update -y && apt-get upgrade -y
RUN apt-get install wget -y
RUN apt-get install bzip2 -y
RUN wget http://dl.4players.de/ts/releases/3.1.2/teamspeak3-server_linux_amd64-3.1.2.tar.bz2
RUN tar xvf teamspeak3-server_linux_amd64-3.1.2.tar.bz2
RUN rm teamspeak3-server_linux_amd64-3.1.2.tar.bz2
EXPOSE 9987/udp 10011 30033
CMD ["sh", "teamspeak3-server_linux_amd64/ts3server_minimal_runscript.sh"]

# https://www.hostinger.com/tutorials/how-to-make-a-teamspeak-3-server/
# apt-get update && apt-get upgrade : Before proceeding, it’s best to check if your system is up to date.
# apt-get install wget : wget is a computer program that retrieves content from web servers. To download TeamSpeak server.
# apt-get install bzip2 : bzip2 is an open-source file compression program. To unzip TeamSpeak server.
# https://docs.docker.com/samples/library/teamspeak/
# EXPOSE : docker port command.  When writing your Dockerfiles, the instruction EXPOSE tells Docker the running container listens on specific network ports.
# CMD : the commands and parameter specified by CMD in your Dockerfiles would be excuted. 
# NOTE: There can only be one CMD instruction in a Dockerfile. If you list more than one CMD, then only the last CMD will take effect.

# docker build -t ex01 .
# docker run -it --rm --name ex1 -e TS3SERVER_LICENSE=accept -p 9987:9987/udp -p 10011:10011 -p 30033:30033 teamspeak

# https://www.hostinger.com/tutorials/how-to-make-a-teamspeak-3-server/
