# Morpheus Monitoring

## Quickstart

```
# Clone the repo
git clone https://github.com/tryfan/ansible-morpheus-monitoring
# Make a Python virtualenv
python3 -m venv venv
# Activate
source venv/bin/activate
# Install ansible
pip install ansible
# Get Ansible roles and collections
ansible-galaxy install -r roles/requirements.yml --roles-path=roles/
# Copy inventory file
cp inv.dist inv
# Modify inv to point to your Morpheus
### vi inv
# Run playbook - add --ask-become-pass if required to sudo on the target
ansible-playbook -i inv playbook.yml 
```

## The Point

This playbook is made for an all in one Morpheus node on Ubuntu 22.  It will give you Grafana dashboards on the MySQL, Elasticsearch, 
and RabbitMQ services running on that box.  JVM is coming soon.

## How it gets there

This playbook installs docker engine on the Morpheus all in one node.  It then configures and installs the following containers:
```
grafana/grafana
prom/prometheus
prom/mysqld-exporter
quay.io/prometheuscommunity/elasticsearch-exporter:latest
```
Since they are all accessing services only available on localhost, they run with `network_mode: host`.  


