FROM docker:19.03-rc

RUN apk --update add openjdk8-jre git openssl openssh bash ca-certificates \
    && update-ca-certificates \
    && wget -O swarm-client.jar https://repo.jenkins-ci.org/releases/org/jenkins-ci/plugins/swarm-client/3.3/swarm-client-3.3.jar \
    && rm -rf /var/cache/apk/*

COPY entrypoint.sh /
RUN chmod +x /entrypoint.sh  \
    && sed -i -e 's/\r$//' /entrypoint.sh

CMD ["/entrypoint.sh"]
