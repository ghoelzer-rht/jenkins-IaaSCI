# Use latest jbossrhek6 image as the base
FROM jbossrhel6:latest

# Add the EAP distribution to /opt/jboss
# Make sure the distribution is copied to directory where Dockerfile is located
COPY jboss-eap-6.1.1.zip /opt/jboss/jboss-eap-6.1.1.zip
RUN cd /opt/jboss
RUN unzip jboss-eap-6.1.1.zip
RUN mv /opt/jboss/jboss-eap-6.1 /opt/jboss/eap-6.1 

# Set the JBOSS_HOME env variable
ENV JBOSS_HOME /opt/jboss/eap-6.1

# Expose the ports we're interested in
EXPOSE 8080 9990

# Set the default command to run on boot
# This will boot EAP  in the standalone mode and bind to all interface
CMD ["/opt/jboss/eap-6.1/bin/standalone.sh", "-b", "0.0.0.0"]

