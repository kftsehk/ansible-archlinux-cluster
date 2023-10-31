# Ansible for Archlinux

This repository uses ansible and various roles to config Archlinux workstation with GPU for quite general purpose:

- Deep Learning
- Scientific computing
- Web and AWS cloud development

# Baseline OS config

Minimal archlinux with network, `sshd` and `yay` installed.

# Usage

1. Install ansible on a master machine (the machine that invoke ansible command)

```
# Install prerequisite
sudo subscription-manager repos --enable ansible-2-for-rhel-8-x86_64-rpms
sudo dnf -y install ansible
```

2. Clone this repository

```
git clone https://github.com/kftsehk/ansible-for-hpc.git
```

3. Install additional roles and collections from ansible-galaxy

```
ansible-galaxy collection install -r requirements.yml
ansible-galaxy install -r requirements.yml
```

4. Invoke ansible-playbook

```
ansible-playbook -i inventory.default.yml -u maintenance --private-key maintenance_key/id_rsa --ssh-extra-args "-o StrictHostKeyChecking=no" -f 10 arch-node.yml
```
