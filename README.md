# role-chrony

Ansible role to install and configure Chrony.

The role is fully generic and supports all the Chrony settings

## Requirements

The role requires RHEL/CentOS 7 to work.

## Role Variables

The variables are fully documented in the [default configuration](defaults/main.yml) file, including their default values and some examples. This file contains all the settings that can be configured.

Please refer to the default configuration file for the full list and use Linux man pages if you need more information on Chrony.

A list of the most generic variable is the following:

| Variable                 | Default | Description                                       |
| :---                     | :---    | :---                                              |
| `chrony_version`         | `''`    | Version of chrony to install                      |
| `chrony_force_restart`   | `false` | If set to `true` it will force Chrony to restart. |

All the other variables are a mapping of Chrony's settings.

## Example Playbook

Using the role without any specific configuration is very simple:

```Yaml
- hosts: servers
  vars:
    chrony_conf_servers:
     - { hostname: vmntp01.example.com, iburst: yes }
     - { hostname: vmntp02.example.com, iburst: yes }
  roles:
   - role: chrony
```

## License

MIT

## Author Information

[Fabrizio Colonna](colofabrix@tin.it)

## Contributors

Pull requests are also very welcome. Please create a topic branch for your proposed changes. If you don't, this will create conflicts in your fork after the merge.