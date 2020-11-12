FROM debian:bullseye
WORKDIR /home/cozy 

RUN apt-get -y update && apt-get -y install wget curl imagemagick && wget -O /usr/local/bin/cozy-stack https://github.com/cozy/cozy-stack/releases/download/1.4.13/cozy-stack-linux-arm && chmod +x /usr/local/bin/cozy-stack

# Add cozy user and directories
RUN useradd -M cozy && mkdir -p /etc/cozy/keys && chown -hR cozy /etc/cozy && chown -hR cozy /home/cozy && mkdir -p /var/lib/cozy && chown -hR cozy /var/lib/cozy

# Change to non-root user
USER cozy

# Start cozy-stack serve
CMD ["/usr/local/bin/cozy-stack","serve"]
