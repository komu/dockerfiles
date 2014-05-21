[Jenkins](http://jenkins-ci.org/) running on Java 8.

Following tools are installed on the system:

  - Java 6 (environment variable: JAVA6_HOME)
  - Java 7 (environment variable: JAVA7_HOME)
  - Java 8 (environment variable: JAVA8_HOME, JAVA_HOME)
  - Git
  - Docker

Running:

    docker run -p 8080:8080 -v /path/to/jenkins/home:/var/lib/jenkins komu/jenkins
