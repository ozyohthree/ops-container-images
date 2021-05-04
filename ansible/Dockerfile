FROM registry.access.redhat.com/ubi8:latest

RUN yum install -y python3-pip git && \
    /usr/bin/pip3 install ansible github3.py openshift && \
    yum clean all -y
