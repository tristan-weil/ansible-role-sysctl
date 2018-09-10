# Ansible Role: sysctl

An Ansible Role to update sysctl parameters.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    sysctl_list: []                                 # the list of sysctl parameters
      - name:                                       # the name of the parameter
        value:                                      # the value
        state: present                              # present|absent

A list of sysctl parameters can be used to update the machine behaviour.
Each item in the list must include the `name` of the sysctl parameter and its `value`.

    sysctl_reload: True                             # True|False

By default at the end of the role, all custom sysctl parameters are applied but this can be turned off.

## Dependencies

None.

## Example Playbook

    - hosts: webservers
      roles:
        - role: t18s.fr_sysctl
          sysctl_list:
            - name: kern.maxfiles
              value: 65536

## Todo

None.

## License

```
Copyright (c) 2018 Tristan Weil <titou@lab.t18s.fr>

Permission to use, copy, modify, and distribute this software for any
purpose with or without fee is hereby granted, provided that the above
copyright notice and this permission notice appear in all copies.

THE SOFTWARE IS PROVIDED "AS IS" AND THE AUTHOR DISCLAIMS ALL WARRANTIES
WITH REGARD TO THIS SOFTWARE INCLUDING ALL IMPLIED WARRANTIES OF
MERCHANTABILITY AND FITNESS. IN NO EVENT SHALL THE AUTHOR BE LIABLE FOR
ANY SPECIAL, DIRECT, INDIRECT, OR CONSEQUENTIAL DAMAGES OR ANY DAMAGES
WHATSOEVER RESULTING FROM LOSS OF USE, DATA OR PROFITS, WHETHER IN AN
ACTION OF CONTRACT, NEGLIGENCE OR OTHER TORTIOUS ACTION, ARISING OUT OF
OR IN CONNECTION WITH THE USE OR PERFORMANCE OF THIS SOFTWARE.
```
