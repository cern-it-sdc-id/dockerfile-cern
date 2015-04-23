FROM centos:7
MAINTAINER CERN


# Add cern repos
RUN curl http://linux.web.cern.ch/linux/centos7/CentOS-CERN.repo -o /etc/yum.repos.d/CentOS-CERN.repo \
	&& curl http://linuxsoft.cern.ch/cern/centos/7/os/x86_64/RPM-GPG-KEY-cern -o /tmp/RPM-GPG-KEY-cern \
	&& /usr/bin/rpm --import /tmp/RPM-GPG-KEY-cern \
	&& /usr/bin/yum --enablerepo=*-testing clean all \
	&& rm /tmp/RPM-GPG-KEY-cern \
	&& rm -rf /var/cache/yum
	
# Add EPEL repos
RUN curl http://mirror.switch.ch/ftp/mirror/epel/7/x86_64/e/epel-release-7-5.noarch.rpm	 -o /tmp/epel-release-7-5.noarch.rpm \
	&& yum localinstall /tmp/epel-release-7-5.noarch.rpm -y \
	&& /usr/bin/yum --enablerepo=*-testing clean all \
	&& rm /tmp/epel-release-7-5.noarch.rpm \
	&& rm -rf /var/cache/yum	
	
# install relevant CERN packages for docker containers
RUN /usr/bin/yum install -y CERN-CA-certs cern-get-keytab cern-wrappers 
    && /usr/bin/yum --enablerepo=*-testing clean all \
    && rm -rf /var/cache/yum	
	


