FROM centos

MAINTAINER diodonfrost diodonfrost@protonmail.com

# System et requirement install
RUN yum update -y; \
yum install vim mlocate git nmap gcc gcc-c++ libxml2-devel libxslt-devel make zsh rpm-build net-tools wget curl epel-release -y; \
yum groupinstall "Development Tools" -y; \
yum install readline-devel zlib-devel libffi-devel libyaml-devel openssl-devel sqlite-devel -y

# Install puppet-agent
RUN rpm -Uvh https://yum.puppetlabs.com/puppet5/puppet5-release-el-7.noarch.rpm; \
yum install puppet-agent -y

# Ruby
RUN curl -sSL https://rvm.io/mpapis.asc | gpg --import -
RUN curl -L get.rvm.io | bash -s stable

#Set env just in case
ENV PATH /usr/local/rvm/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin

#source /etc/profile.d/rvm.sh; \
#rvm reload; \

RUN /bin/bash -l -c "rvm requirements run"
RUN /bin/bash -l -c "rvm install 2.2.5"
RUN /bin/bash -l -c "rvm use 2.2.5 --default"
RUN /bin/bash -l -c "gem install beaker bundle rake --no-ri --no-rdoc"

# Anexe
RUN mkdir /tmp/share; \
updatedb

