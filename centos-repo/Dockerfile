FROM centos

MAINTAINER diodonfrost diodonfrost@protonmail.com

# System et requirement install
RUN yum -y install createrepo epel-release firewalld rsync; \
yum -y install nginx; \
yum -y update

# create directories and initialize repos
RUN mkdir -p /var/www/html/repos/centos/7/{os/x86_64,updates/x86_64}; \
mkdir -p /var/www/html/repos/epel/7/x86_64; \
createrepo /var/www/html/repos/centos/7/os/x86_64/; \
createrepo /var/www/html/repos/centos/7/updates/x86_64/
#createrepo /var/www/html/repos/epel/7/x86_64/

ADD files/nginx.conf /etc/nginx/nginx.conf

# initialize repos
RUN rsync -avz --exclude='repo*' rsync://centos.bhs.mirrors.ovh.net/ftp.centos.org/7/os/x86_64/ /var/www/html/repos/centos/7/os/x86_64/
RUN rsync -avz --exclude='repo*' rsync://centos.bhs.mirrors.ovh.net/ftp.centos.org/7/updates/x86_64/ /var/www/html/repos/centos/7/updates/x86_64/
#RUN rsync -avz --exclude='repo*' --exclude='debug' rsync://mirrors.rit.edu/epel/7/x86_64/ /var/www/html/repos/epel/7/x86_64/

# Update repo
RUN createrepo --update /var/www/html/repos/centos/7/os/x86_64/
RUN createrepo --update /var/www/html/repos/centos/7/updates/x86_64/
#RUN createrepo --update /var/www/html/repos/epel/7/x86_64/
