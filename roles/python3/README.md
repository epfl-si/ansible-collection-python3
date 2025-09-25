# epfl_si.python3.python3

## Description

An Ansible role to install Python 3 and make it available in the `PATH` on the target host. Based on [pyenv](https://github.com/pyenv/pyenv). Doesn't require root (or Python) to be installed remotely.

## Variables

|Variable Name|Default Value|Description|
|:---|:---:|:---:|:---|:---|
|`python3_pyenv_dir`|"$HOME/.pyenv"|The path to install pyenv into. Shell variables, if any, will be expanded. |
|`python3_version`|"3.6"|The version of Python to install. ⚠ Should be a string, rather than a number (in particular if you want to install version 3.10)|
|`python3_shell_init_file`|"$HOME/.bash_profile"|The shell script to install pyenv variables into. Shell variables, if any, will be expanded. Set to undefined (`~` in YAML) to disable `pyenv init` functionality.|

## Tags

|Tag  Name|Description|
|:---|:---|
|`python3.uninstall`|Uninstall everything previously set up by this role.|


## Playbook Examples

### Standard Role Usage

```yaml
---
- name: Install Python 3 via pyenv
  hosts: all
  gather_facts: no   # Recommended, in case there isn't already Python 3 on the other end
  roles:
    - role: epfl_si.python3.python3
      vars:
        python3_version: "3.10"
```

## License

GPLv2 or (at your option) any later version of the GPL

## Author

[EPFL ISAS-FSD](mailto:isas-fsd@groupes.epfl.ch)
