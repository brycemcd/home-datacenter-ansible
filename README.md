Ansible Playbooks for Hadoop

This is very much a work in progress. It began as a means to test a hadoop proof
of concept at my job. I've since bootstrapped a small hadoop/spark
cluster in my home an  I use these playbooks/templates to keep the
cluster up to date.


## Bootstrap a Cluster

### Manual Steps

* Install Ubuntu 16.04 LTS (latest LTS release).
* Make sure install has a brycemcd user

```bash
useradd -m brycemcd
```
* Install ssh public key in ~/.ssh/authorized_keys to permit
  password-less login

```bash
su brycemcd
ssh-keygen
cd .ssh
curl https://github.com/brycemcd.keys -o authorized_keys
```
* run visudo and give the brycemcd user passwordless sudo access

`brycemcd ALL=(ALL:ALL) NOPASSWD:ALL`

* Add 
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
|pascal|host|canada hosted|Cloud at Cost: a cheap public IP address with a shoddy service|pascal.thedevranch.net|
|lovelace|service|nyc01|Elasticsearch|es01.thedevranch.net|
|spark4 (legacy - needs update!)|service|nyc01|Mosquitto|mqtt01.thedevranch.net mqtt02.thedevranch.net|
|turing|service|beav01|Elasticsearch|es02.thedevranch.net|
|lovelace|service|nyc01|postgres service|psql01.tthedevranch.net|
|spark4 (legacy)|service|nyc01|postgres service|psql02.tthedevranch.net|
|spark3 (legacy)|service|nyc01|postgres service|psql03.tthedevranch.net|
|lovelace|service|nyc01|redis service|redis01.tthedevranch.net|
