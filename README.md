# Homelab Ansible

![Ansible CI](https://github.com/NicolaiMatthew/homelab-ansible/actions/workflows/ansible-lint.yml/badge.svg)

Infrastructure automation for my Proxmox homelab.

## Playbooks

| Playbook | Description |
|---|---|
| `facts.yml` | Gather system info from all hosts |
| `update-all.yml` | Update all LXCs simultaneously |
| `apply-base.yml` | Apply base configuration role |
| `provision-lxc.yml` | Provision a new LXC from scratch |

## Roles

| Role | Description |
|---|---|
| `base` | SSH hardening, packages, MOTD, unattended upgrades |

## Usage
```bash
# Update all machines
ansible-playbook playbooks/update-all.yml

# Apply base config
ansible-playbook playbooks/apply-base.yml

# Provision new LXC
ansible-playbook playbooks/provision-lxc.yml --ask-vault-pass -e @inventory/vault.yml
```

## Requirements
- Ansible 2.x+
- community.proxmox collection
- proxmoxer Python library
