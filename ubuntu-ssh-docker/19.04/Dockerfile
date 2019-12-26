# docker build -t jooas/ubuntu-ssh-docker:19.04 .
# docker push jooas/ubuntu-ssh-docker:19.04

FROM jooas/ubuntu-ssh:19.04

RUN apt-get update
RUN apt-get install apt-transport-https ca-certificates curl gnupg-agent software-properties-common

RUN curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
RUN add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"

RUN apt-get update
RUN apt-get install docker-ce docker-ce-cli containerd.io

CMD ["/usr/sbin/sshd", "-D"]
EXPOSE 22