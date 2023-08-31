# Use a base image with Java installed
FROM openjdk:8-jre

# Set the environment variables
ENV JMETER_HOME /opt/apache-jmeter-5.6
ENV PATH $JMETER_HOME/bin:$PATH

# Download and install JMeter
RUN mkdir -p $JMETER_HOME && \
    curl -L https://archive.apache.org/dist/jmeter/source/apache-jmeter-5.6_src.tgz | tar xvz --strip-components=1 -C $JMETER_HOME


# Set the working directory
WORKDIR $JMETER_HOME/bin

# Add jmeter to the PATH
RUN echo "export PATH=$PATH" >> /etc/environment

# Command to run JMeter
CMD ["java", "-jar", "ApacheJMeter.jar"]