# Quick Hack on firewalld setup  with customizable rules

# Usage

Define the Configuration hash some place . Check Examples at defaults/main.yml.ex

## Configuration Capabilities
[Check manual for details](http://docs.ansible.com/ansible/latest/firewalld_module.html)
```yaml
firewalld:
  configuration:
    input_ports:               # list of zones/protocols/ports to open
      - { zone: "public", protocol: "tcp", port: "22"}
      - { zone: "public",
          protocol: "tcp",
          port: "34",
          source: "192.168.33.0/24"     # sorce can be ommited, default 0.0.0.0/0
          }
     extra_ports :
       - { zone: "public", protocol: "tcp", port: "2377"}
       - { zone: "public", protocol: "tcp", port: "7946"}
       - { zone: "public", protocol: "udp", port: "7946"}
       - { zone: "public", protocol: "udp", port: "4789"}

```

Also there is one extra variable to allow the role to be more flexible

```yaml
- hosts:
    - some_group
  roles:
     - { role: firewalld }
```

# License

GNU GPLv3 

# Author Information

Created by Miguel Rodrigues
