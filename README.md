# [networkd Bridge Ansible Role][1]

[![test & release][2]][3]

Ansible role to create a virtual bridge network interface with systemd-networkd.

## Requirements

Hosts which run this role should have systemd-networkd set as their active
network manager.

## Role Variables

<table>
<tr><th>Name</th><th>Required</th><th>Type / Choices</th><th>Description</th></tr>
<tr><td><code>networkd_bridge_name</code></td>
<td>no</td>
<td>string</td>
<td>

Name of the virtual network bridge.

**Default:** `"bridge01"`
</td></tr>


<tr><td><code>networkd_bridge_interface</code></td>
<td>no</td>
<td>string</td>
<td>

Name of the physical interface, the bridge should be connected to.

**Default:** `"eth0"`
</td></tr>


<tr><td><code>networkd_bridge_ip_address</code></td>
<td>no</td>
<td>string or `false`</td>
<td>

A static IPv4 address that should be configured on the bridge, so that the host
can be reached through the physical interface that is configured as bridge. A
falsy value causes the bridge to use DHCP instead.

**Default:** `false`
</td></tr>
</table>

## Dependencies

None.

## Example Playbook

```yaml
- hosts: all
  tasks:
    - ansible.builtin.import_role:
        name: gliech.networkd_bridge
```

## License

This project is licensed under the terms of the [GNU General Public License v3.0](LICENSE)

[1]: https://galaxy.ansible.com/ui/standalone/roles/gliech/networkd_bridge/
[2]: https://github.com/gliech/networkd-bridge-ansible-role/actions/workflows/release.yml/badge.svg
[3]: https://github.com/gliech/networkd-bridge-ansible-role/actions/workflows/release.yml
[4]: https://github.com/gliech/semantic-release-config-github-ansible-role
