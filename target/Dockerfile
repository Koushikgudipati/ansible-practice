FROM centos

RUN yum -y install openssh-server

RUN useradd target_user && \
  echo "asdf" | passwd target_user --stdin && \
  mkdir /home/target_user/.ssh && \
  chmod 700 /home/target_user/.ssh

COPY key.pub /home/target_user/.ssh/authorized_keys

RUN chown -R target_user:target_user /home/target_user/.ssh && \
  chmod 600 /home/target_user/.ssh/authorized_keys

RUN /usr/sbin/sshd-keygen

CMD /usr/sbin/sshd -D
