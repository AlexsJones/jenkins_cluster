FROM jenkins
USER root
RUN apt-get update && apt-get install -y vim socat cron sudo docker.io
RUN sed -i 's/^.sudo.*/%sudo ALL=(ALL:ALL) NOPASSWD:ALL/' /etc/sudoers
RUN adduser jenkins sudo
RUN adduser jenkins docker
USER jenkins
RUN /usr/local/bin/install-plugins.sh github
RUN /usr/local/bin/install-plugins.sh docker-plugin
RUN /usr/local/bin/install-plugins.sh saferestart
ENV JENKINS_MIRROR http://mirrors.jenkins-ci.org
ENV JAVA_OPTS="-Djenkins.install.runSetupWizard=false -Xmx2048m"
