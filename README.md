# Ansible Role: sysctl

An Ansible Role to update sysctl parameters.

**NOTE**: it does not work on Docker.

[![Actions Status](https://github.com/tristan-weil/ansible-role-sysctl/workflows/molecule/badge.svg?branch=master)](https://github.com/tristan-weil/ansible-role-sysctl/actions)

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| sysctl_list   | []      | a list of <*sysctl_entries*> |
| sysctl_reload | True    | *True / False*: reload the configuration |

### <*sysctl_entries*>

A list of sysctl parameters can be used to update the machine behaviour.

Mandatory variables:

| Variable      | Description |
| :------------ | :---------- |
| name          | the name of the parameter |
| value         | the value of the parameter |

Optional variables:

| Variable      | Default | Description |
| :------------ | :------ | :---------- |
| state         | present | *present / absent* : the state of the entry |

## Example Playbook

    - hosts: 'webservers'
      roles:
        - role: 'ansible-role-sysctl'
          sysctl_list:
            - name: 'kern.maxfiles'
              value: 65536

## Todo

None.

## Dependencies

None.

## Supported platforms

See [meta/main.yml](https://github.com/tristan-weil/ansible-role-sysctl/blob/master/meta/main.yml)

## License

See [LICENSE.md](https://github.com/tristan-weil/ansible-role-sysctl/blob/master/LICENSE.md)
