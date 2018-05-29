FROM debian:jessie

RUN  apt-get update && apt-get install -y openssl

ENV OPENSSL_SUBJ="/C=US/ST=California/L=Santa Clara"
ENV OPENSSL_CA="${OPENSSL_SUBJ}/CN=fake-CA"
ENV OPENSSL_SERVER="${OPENSSL_SUBJ}/CN=fake-server"
ENV OPENSSL_CLIENT="${OPENSSL_SUBJ}/CN=fake-client"

COPY gencerts.sh /
RUN chmod +x /gencerts.sh

VOLUME /certs

WORKDIR /certs

CMD /gencerts.sh