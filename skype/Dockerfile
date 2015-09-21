# Mostly copied from:
# https://github.com/jfrazelle/dockerfiles/blob/7771ae9e988c7f15b57741342da2196020410f33/skype/Dockerfile

FROM debian:jessie

RUN dpkg --add-architecture i386 && \
	apt-get update && \
	apt-get install -y curl --no-install-recommends

RUN curl http://download.skype.com/linux/skype-debian_4.3.0.37-1_i386.deb > /tmp/skype.deb && \
	dpkg --force-depends -i /tmp/skype.deb && \
	apt-get install -fy

COPY run /run-skype
RUN chmod +x /run-skype

ENTRYPOINT ["/run-skype"]
