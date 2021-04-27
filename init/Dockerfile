FROM fluent/fluent-bit:1.7-debug
USER root

# Install build tools
#RUN ["sh", "-c", "apt-get -qq update"] #&& \
#    sh -c apt-get install -y -qq curl ca-certificates build-essential cmake iputils-ping dnsutils make bash sudo wget unzip nano vim valgrind  && \
#    sh -c apt-get install -y -qq --reinstall lsb-base lsb-release

COPY fluent-bit.conf /fluent-bit/etc/
COPY parsers.conf /fluent-bit/etc/

CMD ["/fluent-bit/bin/fluent-bit", "-c", "/fluent-bit/etc/fluent-bit.conf", "-vv"]