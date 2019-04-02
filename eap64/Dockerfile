#FROM registry.access.redhat.com/jboss-eap-7/eap72-openshift
FROM registry.access.redhat.com/jboss-eap-6/eap64-openshift

MAINTAINER Nikhil Malvankar nmalvank@redhat.com

ENV DB_USERNAME=sa \
    DB_PASSWORD=sa \
    JBOSS_LOG_LEVEL=DEBUG

USER root

COPY custom-eap64/configuration/standalone-openshift.xml /opt/eap/standalone/configuration
COPY custom-eap64/deployments/jboss-helloworld.war /opt/eap/standalone/deployments

RUN chown jboss:jboss /opt/eap/standalone/configuration/standalone-openshift.xml
RUN chown jboss:jboss /opt/eap/standalone/deployments/jboss-helloworld.war

USER jboss

#CMD ["/opt/eap/bin/standalone.sh", "-c", "standalone-poc.xml", "-b", "0.0.0.0", "-bmanagement", "0.0.0.0"]
