FROM ubuntu:14.04

MAINTAINER juha.komulainen@evident.fi

# First make sure the base system is up-to-date
RUN apt-get update
RUN apt-get -y upgrade

# First add a repository containing Java 8
ADD webupd8team-java.list /etc/apt/sources.list.d/
RUN apt-key adv --keyserver keyserver.ubuntu.com --recv-keys C2518248EEA14886
RUN apt-get update

# Accept the Java licenses
RUN echo oracle-java6-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN echo oracle-java7-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections
RUN echo oracle-java8-installer shared/accepted-oracle-license-v1-1 select true | /usr/bin/debconf-set-selections

# Install different Java versions
RUN apt-get -y install oracle-java6-installer
RUN apt-get -y install oracle-java7-installer
RUN apt-get -y install oracle-java8-installer

# Ensure Java 8 is the default version
RUN update-java-alternatives -s java-8-oracle

# Set environment variables pointing to different Java installations
ENV JAVA_HOME /usr/lib/jvm/java-8-oracle
ENV JAVA6_HOME /usr/lib/jvm/java-6-oracle
ENV JAVA7_HOME /usr/lib/jvm/java-7-oracle
ENV JAVA8_HOME /usr/lib/jvm/java-8-oracle

# Download Jenkins
ADD http://mirrors.jenkins-ci.org/war/1.563/jenkins.war /opt/jenkins.war

ENV JENKINS_HOME /jenkins

ENTRYPOINT ["java", "-jar", "/opt/jenkins.war"]
EXPOSE 8080
VOLUME ["/jenkins"]
CMD [""]
