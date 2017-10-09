FROM ubuntu

MAINTAINER diodonfrost diodonfrost@protonmail.com

# System et requirement install
RUN apt update; \
apt install software-properties-common vim git nmap whois -y

# Python
RUN apt-add-repository ppa:ansible/ansible -y; \
apt update; \
apt install python-pip -y; \

# Ansible
apt install ansible -y; \
pip install --upgrade pip; \
pip install pyvmomi

RUN pip install python-openstackclient python-neutronclient python-manilaclient
 
