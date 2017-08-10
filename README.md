# Quick Hack on firewalld setup  with customizable rules

# Usage

Replace the defaults in defaults/main.yml, or provide variables definition by other way ( group_var, command line arguments, .... )

also there is one extra variable to allow the role to be more flexible

```
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

Created by Miguel Rodrigues.
