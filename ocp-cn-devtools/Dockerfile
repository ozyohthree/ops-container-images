FROM registry.access.redhat.com/ubi8/podman

LABEL name="ocp-cn-devtools" \
      version="0.0.1" \
      release="1" \
      summary="A generic container for openshift containerization workflow." \
      description="A generic container with common tools for developing container applications openshift."

RUN dnf update -y && \
    dnf install -y git python3-pip python3-cryptography nodejs npm vim && \
    dnf clean all -y && \
    /usr/bin/pip3 install --no-cache-dir ansible github3.py openshift && \
    curl -o /tmp/openshift-client-linux.tar.gz https://mirror.openshift.com/pub/openshift-v4/clients/ocp/latest/openshift-client-linux.tar.gz && \
    tar -xzvf /tmp/openshift-client-linux.tar.gz -C /usr/local/bin/ && \
    chmod +x /usr/local/bin/oc && \
    rm /usr/local/bin/README.md && \
    rm /usr/local/bin/kubectl && \
    rm /tmp/openshift-client-linux.tar.gz && \
    curl -s "https://raw.githubusercontent.com/helm/helm/main/scripts/get-helm-3" | bash && \
    mv /usr/local/bin/helm /usr/bin/helm && \
    curl -s "https://raw.githubusercontent.com/kubernetes-sigs/kustomize/master/hack/install_kustomize.sh"  | bash && \
    mv ./kustomize /usr/bin/kustomize

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash