# docker build -t jooas/ubuntu-ssh:19.04 .
# docker push jooas/ubuntu-ssh:19.04

FROM ubuntu:19.04

RUN apt-get update
RUN apt-get upgrade -y
RUN apt-get install -y openssh-server

RUN mkdir /var/run/sshd
RUN mkdir /root/.ssh

RUN echo 'root:root' | chpasswd

RUN sed -ri 's/^#?PermitRootLogin\s+.*/PermitRootLogin yes/' /etc/ssh/sshd_config
#RUN sed -ri 's/^#?ChallengeResponseAuthentication\s+.*/ChallengeResponseAuthentication yes/' /etc/ssh/sshd_config
#RUN sed -ri 's/UsePAM yes/#UsePAM yes/g' /etc/ssh/sshd_config

CMD ["/usr/sbin/sshd", "-D"]
EXPOSE 22