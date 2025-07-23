# network.healthchecks.ip_reachability

## Overview
The `network.healthchecks.ip_reachability` role allows monitoring of IP reachability from network devices. This helps detect connectivity issues and ensures network paths are functioning properly. The role provides a comprehensive health check view that shows the status of IP reachability tests and overall network connectivity health.

## Features
- Monitor IP reachability with configurable targets
- Test connectivity to multiple IP addresses
- Generate alerts for unreachable destinations
- Configurable ping count and timeout settings

## Variables
| Variable Name   | Default Value | Required | Type  | Description                                      |
|----------------|--------------|----------|-------|--------------------------------------------------|
| `ip_targets` | []     | yes       | list   | List of IP addresses to ping from the device. |
| `count` | 2     | no       | int   | Number of ping packets to send (default: 2). |

## Usage

### Example: Monitoring IP Reachability
```yaml
- name: Run IP reachability test
  ansible.builtin.include_role:
    name: network.healthchecks.ip_reachability
  vars:
    ip_targets:
      - 8.8.8.8
      - 1.1.1.1
      - 208.67.222.222
    count: 3
  register: reachability_result

- name: Display IP reachability health check results
  ansible.builtin.debug:
    var: reachability_result.health_checks
```

### Output: IP Reachability Health Check Status
```json
{
    "health_checks": {
        "ip_reachability": {
            "status": "PASS",
            "reachable_targets": ["8.8.8.8", "1.1.1.1"],
            "unreachable_targets": [],
            "total_targets": 2,
            "reachable_count": 2
        },
        "result": "PASS"
    }
}
```

### Health Check Status
- `result`: Overall health check result
  - `PASS`: All IP targets are reachable
  - `FAIL`: One or more IP targets are unreachable
- `ip_reachability`: IP reachability metrics
  - `status`: Individual reachability check status
  - `reachable_targets`: List of successfully pinged IP addresses
  - `unreachable_targets`: List of unreachable IP addresses
  - `total_targets`: Total number of IP targets tested
  - `reachable_count`: Number of successfully reached targets

## Supported Platforms

- Cisco IOS
- Cisco NX-OS
- Juniper Junos
- Cisco IOS-XR

## License

GNU General Public License v3.0 or later.

See [LICENSE](https://www.gnu.org/licenses/gpl-3.0.txt) to see the full text.

## Author Information

- Ansible Network Content Team
