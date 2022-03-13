FROM ubuntu:latest
WORKDIR /home/ubuntu/ansible-files
RUN mkdir /var/run/sshd
COPY ./ansible-files .
RUN apt-get update
RUN apt-get install -y ansible
RUN apt-get install -y openssh-server
EXPOSE 22
CMD ["/usr/sbin/sshd", "-D"]