FROM registry.access.redhat.com/ubi8:latest

RUN yum install -y python3-pip python3-cryptography git && \
    /usr/bin/pip3 install ansible github3.py openshift && \
    yum clean all -y

ENTRYPOINT ["/usr/local/bin/ansible-playbook"]
