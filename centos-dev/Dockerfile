FROM centos

MAINTAINER diodonfrost diodonfrost@protonmail.com

# System et requirement install
RUN yum update -y; \
yum install vim git zsh wget curl nmap gcc make tcpdump rpm-build net-tools epel-release -y; \
yum install python-jinja2 python-yaml asciidoc python-setuptools python2-devel -y; \
yum install python-pip -y

# Python
RUN pip install --upgrade pip; \
pip install pyvmomi; \
pip install python-openstackclient python-neutronclient python-heatclient python-manilaclient

# Ansible
RUN git clone git://github.com/ansible/ansible.git
WORKDIR ansible
RUN make rpm; \
yum install rpm-build/ansible-*.noarch.rpm -y; \
yum install -y https://yum.puppetlabs.com/puppetlabs-release-pc1-el-7.noarch.rpm

# Install puppet-agent
yum install puppet-agent -y; \
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"

