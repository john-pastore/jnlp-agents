FROM jenkins/jnlp-slave:alpine as jnlp

FROM python:alpine

RUN apk -U add openjdk8-jre && \
    rm -rf /var/cache/apk/*

COPY --from=jnlp /usr/local/bin/jenkins-agent /usr/local/bin/jenkins-agent
COPY --from=jnlp /usr/share/jenkins/agent.jar /usr/share/jenkins/agent.jar

ENTRYPOINT ["/usr/local/bin/jenkins-agent"]
