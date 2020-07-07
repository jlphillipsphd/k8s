FROM jupyterhub/k8s-hub:0.9.0
LABEL maintainer="Joshua L. Phillips <https://www.cs.mtsu.edu/~jphillips/>"

USER root

RUN apt-get update && \
    DEBIAN_FRONTEND=noninteractive apt-get install -y --no-install-recommends \
    xinetd \
    ssh \
    ldap-utils \
    finger \
    wget

# RUN pip install \
#     jupyterhub-kubespawner

# RUN conda install --quiet --yes \
#     pip

# RUN pip3 install wheel

# RUN pip3 install --upgrade \
#     jupyterhub

# XINETD - SSH port forward for LDAP
COPY ldap /etc/xinetd.d/.
RUN mkdir /root/.ssh
COPY known_hosts /root/.ssh/.
