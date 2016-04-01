# Install concourse CI easily on one host

### Description

["Concourse"](https://github.com/concourse/concourse-lite) is a cool CI tool that treats pipelines and containers as a first line citizens.
### Requirements

Install Ansible `2.0+`, you can use [this](http://docs.ansible.com/ansible/intro_installation.html) instruction or install ansible using `pip` (the following example installs Ansible to fresh Ubuntu):
```
sudo apt-get update
sudo apt-get install python-pip python-dev -y
sudo pip install ansible
```

### How to use

You will need to install the role, create 2 files and run one command:

```bash
ansible-galaxy install allomov.concourse

cat <<EOF > playbook.yml
---
- hosts: concourse
  roles: 
  - role: allomov.concourse
EOF

cat <<EOF > hosts
[concourse]
$TARGET_MACHINE_IP_ADDREES ansible_connection=local
EOF

ansible-playbook -i hosts playbook.yml
```

Enjoy! You can go for a cup a coffee now.
