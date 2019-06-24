FROM centos

RUN curl -O https://bootstrap.pypa.io/get-pip.py  && \
    python get-pip.py && \
    pip install ansible --upgrade

RUN yum -y install openssh-clients

CMD ["tail -f /dev/null"]