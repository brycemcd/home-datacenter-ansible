Ansible Playbooks for Hadoop

This is very much a work in progress. It began as a means to test a hadoop proof
of concept at my job. I've since bootstrapped a small hadoop/spark
cluster in my home an  I use these playbooks/templates to keep the
cluster up to date.

`v1.9/` directory contains work from 2015 when I first began
experimenting with ansible and Hadoop. This is useful as a reference
now.

## Bootstrap a System

### Manual Steps

* Install Ubuntu 16.04 LTS (latest LTS release).
* Make sure install has brycemcd as a sudo
* Give brycemcd passwordless sudo:

`brycemcd ALL=(ALL:ALL) NOPASSWD:ALL`

```bash
useradd -m brycemcd
```
### No Mo' Manual

* Bootstrap the system by running: `ansible-playbook -i ansible_hosts bootstrap_box.yml`


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
|euclid|host|nyc01|old laptop i7, 8GB RAM, ~100GB SSD|euclid.thedevranch.net|
|gauss|host|nyc01|old desktop i5, 16GB RAM, 500GB SSD|gauss.thedevranch.net|
