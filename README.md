# Ansible Collection - epfl_si.python3

This collection currently contains only the `epfl_si.python3.python3`
role, that installs Python 3 on the target host without requiring root (or Python).

Example playbook:

```yaml
- name: Install Python 3 via pyenv
  hosts: all
  gather_facts: no   # You know, in case there isn't already Python 3 on the other end
  roles:
    - role: epfl_si.python3.python3
      vars:
        python3_version: "3.10"   # Mind the quotes - Especially for that particular version!
```

The default value for `python3_version` is "3.6", which is good enough both [for RedHat 6](https://stackoverflow.com/questions/53543477/building-python-3-7-1-ssl-module-failed) and [for ansible-core up to 2.16](https://docs.ansible.com/ansible/latest/reference_appendices/release_and_maintenance.html#ansible-core-support-matrix), which [translates](https://docs.ansible.com/ansible/latest/reference_appendices/release_and_maintenance.html#ansible-community-changelogs) to Ansible 9.x
