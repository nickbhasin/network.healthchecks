Role: ip_reachability

This role verifies IP reachability from a network device using the appropriate platform-specific ping module.

## Supported Platforms

- Cisco IOS
- Cisco NX-OS
- Juniper Junos
- Cisco IOS-XR

## Variables

- `ip_targets`: List of IP addresses to ping from the device.

Example:
```yaml
ip_targets:
  - 8.8.8.8
  - 1.1.1.1
```

## Example Playbook

```yaml
- name: Run reachability test
  hosts: all
  gather_facts: false
  vars:
    ip_targets:
      - 8.8.8.8
      - 1.1.1.1
  roles:
    - ip_reachability
```
