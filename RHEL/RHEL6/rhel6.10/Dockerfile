#FROM koji/image-build
FROM rhel6:6.10

#MAINTAINER Red Hat, Inc.

#LABEL com.redhat.component="rhel-server-container" \
#      name="rhel7" \
#      version="7.8"

#labels for container catalog
#LABEL summary="Provides the latest release of Red Hat Enterprise Linux 7 in a fully featured and supported base image."
#LABEL description="The Red Hat Enterprise Linux Base image is designed to be a fully supported foundation for your containerized applications. This base image provides your operations and application teams with the packages, language runtimes and tools necessary to run, maintain, and troubleshoot all of your applications. This image is maintained by Red Hat and updated regularly. It is designed and engineered to be the base layer for all of your containerized applications, middleware and utilities. When used as the source for all of your containers, only one copy will ever be downloaded and cached in your production environment. Use this image just like you would a regular Red Hat Enterprise Linux distribution. Tools like yum, gzip, and bash are provided by default. For further information on how this image was built look at the /root/anacanda-ks.cfg file."
LABEL io.k8s.display-name="Red Hat Enterprise Linux 7"
LABEL io.openshift.tags="base rhel7"

#ENV container oci
#ENV PATH /usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

RUN yum install http://satellite.zircon.local/pub/katello-ca-consumer-latest.noarch.rpm -y
RUN subscription-manager register --org="Zircon" --activationkey="rhel7"
RUN subscription-manager repos --enable=rhel-7-server-rpms
RUN yum update -y && yum clean all
RUN yum install vim screen insights-client -y

CMD ["/bin/bash"]
