FROM registry.access.redhat.com/ubi8:latest

RUN curl -o /tmp/openshift-client-linux.tar.gz https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz && \
    tar -xzvf /tmp/openshift-client-linux.tar.gz -C /usr/local/bin/ && \
    chmod +x /usr/local/bin/oc && \
    rm /usr/local/bin/README.md && \
    rm /usr/local/bin/kubectl && \
    rm /tmp/openshift-client-linux.tar.gz 

ENTRYPOINT ["/usr/local/bin/oc"]
