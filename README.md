Ansible Role: UFW Firewall
=========

This role installs UFW and configures the local firewall to filter **BOTH** inbound and outbound traffic.

By default, the only inbound traffic accepted is SSH (the port is a variable in this case).

The following outbound traffic is authorized:
- SSH (22/tcp)
- HTTP (80/tcp)
- HTTPS (443/tcp)
- NTP (123/udp)
- HKS (11371/tcp)
- DNS (53/udp)
- SMTPS (587/tcp)


Requirements
------------

No specific requirements for this role.

Role Variables
--------------

The only variable is the SSH port you defined to connect to your server. The role enforces the default port 22/tcp if not modified.

Here is how to configure the variable:

```
ssh_port: 22
```

This variable should either be defined as a group_vars or a host_vars.

Dependencies
------------

No dependencies from other roles required.

Example Playbook
----------------

Here is a simple example playbook to use this role:

```
hosts: all
user: myuser
become: true
roles:
  - { role: ufw, tags: [ 'ufw' ] }
```

License
-------

MIT / BSD

Author Information
------------------

My name is Gaétan. You can follow me on [Twitter](https://twitter.com/astsu777)

Website: [ICT Pour Tous](https://www.ictpourtous.com)
