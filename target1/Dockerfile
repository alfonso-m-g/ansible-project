FROM ubuntu:latest
RUN apt-get update && apt-get install -y openssh-server && apt-get install -y python3-pip
RUN mkdir /var/run/sshd
RUN echo 'root:mypassword' | chpasswd
RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/' /etc/ssh/sshd_config
RUN sed 's@session\s*required\s*pam_loginuid.so@session optional pam_loginuid.so@g' -i /etc/pam.d/sshd
COPY public-key.txt /home/ubuntu/keys
RUN ssh-keygen -t rsa -f /root/.ssh/id_rsa
RUN touch /root/.ssh/authorized_keys
RUN echo $(cat /home/ubuntu/keys) >> /root/.ssh/authorized_keys
EXPOSE 22 80
CMD ["/usr/sbin/sshd", "-D"]