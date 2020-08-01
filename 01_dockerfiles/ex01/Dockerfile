FROM	debian:10.2

RUN	apt update -y && apt upgrade -y && \
	apt install -y wget bzip2 && \
	mkdir /opt/ts3server && \
	wget https://files.teamspeak-services.com/releases/server/3.10.2/teamspeak3-server_linux_amd64-3.10.2.tar.bz2 && \
	tar -xf teamspeak3-server_linux_amd64-3.10.2.tar.bz2 --strip-components=1 -C /opt/ts3server && \
	rm teamspeak3-server_linux_amd64-3.10.2.tar.bz2 && \
	touch /opt/ts3server/.ts3server_license_accepted

EXPOSE	9987/udp 10011 30033

CMD	/opt/ts3server/ts3server_minimal_runscript.sh

# How to build it?
# docker build -t ex01 .

# How to run it?
# docker run --rm -p 9987:9987/udp -p 10011:10011 -p 30033:30033 ex01

# port: 9987/upd  -- Voice
# port: 30033/tcp -- Filetransfer 	
# port: 10011/tcp -- ServerQuery (raw)