# phpdevplaybook

## download and add centos65 box

vagrant box add kirito/centos65 url

vagrant up

## config ssh key

ssh-keygen -t rsa -c "dungntnew@gmail.com"

ssh-copy-id vagrant@192.168.33.15

## run 

ansible-playbook playbook.yml -i ../hosts

