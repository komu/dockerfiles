[Jenkins](http://jenkins-ci.org/) running on Java 8.

Following tools are installed on the system and environment variables are defined for their locations:

  - Java 6 (JAVA6_HOME)
  - Java 7 (JAVA7_HOME)
  - Java 8 (JAVA8_HOME, JAVA_HOME)

Running:

    docker run -p 8080:8080 -v /path/to/jenkins/home:/jenkins komu/jenkins
