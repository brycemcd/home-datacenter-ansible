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
* Bootstrap the system by running: `ansible-playbook -i ansible_hosts
  playbooks/bootstrap_box.yml`
