Ansible Playbooks for Hadoop

This is very much a work in progress. It began as a means to test a hadoop proof
of concept at my job. I've since bootstrapped a small hadoop/spark
cluster in my home an  I use these playbooks/templates to keep the
cluster up to date.


## Bootstrap a Cluster

### Manual Steps

* Install Ubuntu 14.04 LTS (latest LTS release).
* Make sure install has a brycemcd user
* Install ssh public key in ~/.ssh/authorized_keys to permit
  password-less login
* run visudo and give the brycemcd user passwordless sudo access
* Bootstrap the system by running: `ansible-playbook -i ansible_hosts playbooks/bootstrap_box.yml`


## WIP Hostnames

The approach I _should_ take is to name the physical hosts something and
then name the services as cnames to the physical hosts on which they're hosted.

A migration has been started to update to this convention.

http://famous-mathematicians.org/

|host|host or service|location|description|cname|
|----|---------------|--------|-----------|-----|
|lovelace|host|nyc01|red gigabyte brick, AMD proc, 8GB RAM, 120GB SSD|lovelace.thedevranch.net|
|turing|host|beav01|red gigabyte brick, AMD proc, 8GB RAM, 120GB SSD |turing.thedevranch.net|
|lovelace|service|nyc01|Elasticsearch|es01.thedevranch.net|
|lovelace|service|nyc01|Mosquitto|mqtt01.thedevranch.net|
|turing|service|beav01|Elasticsearch|es02.thedevranch.net|
