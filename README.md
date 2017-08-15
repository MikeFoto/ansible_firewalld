# Quick Hack on firewalld setup  with customizable rules

# Usage

Define the Configuration hash some place . Check Examples at defaults/main.yml.ex

## Configuration Capabilities

```yaml
firewalld:
  configuration:
    input_ports:               # list of zones/protocols/ports to open
      - { zone: "public", protocol: "tcp", port: "22"}

```

Also there is one extra variable to allow the role to be more flexible

```yaml
- hosts:
    - some_group
  roles:
     - { role: firewalld,
         extra_ports : [
           { zone: "public", protocol: "tcp", port: "2377"},
           { zone: "public", protocol: "tcp", port: "7946"},
           { zone: "public", protocol: "udp", port: "7946"},
           { zone: "public", protocol: "udp", port: "4789"}
         ]
        }
```

# License

MIT

# Author Information

Created by Miguel Rodrigues
