squid
=====

[![Build Status](https://travis-ci.org/kbrebanov/ansible-squid.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-squid)

Installs Squid

Requirements
------------

This role requires Ansible 1.4 or higher.

Role Variables
--------------

| Name                            | Default         | Description                                                                                            |
|---------------------------------|-----------------|--------------------------------------------------------------------------------------------------------|
| squid_acls                      | []              | List of ACL hashes (keys: name, type, argument)                                                        |
| squid_dns_v4_first              | "off"           | This option reverses the order of preference to make Squid contact dual-stack websites over IPv4 first |
| squid_forwarded_for             | "on"            | Set X-Forwarded-For header in HTTP requests                                                            |
| squid_http_access_allow_clients | ["localhost"]   | List of clients to allow access                                                                        |
| squid_http_port                 | 3128            | The port where Squid will listen for HTTP requests                                                     |
| squid_proxy_only                | false           | If enabled, disables caching                                                                           |
| squid_tcp_outgoing_address      | ''              | Map requests to different outgoing IP address                                                          |

Dependencies
------------

None

Example Playbook
----------------

Install Squid
```
- hosts: all
  roles:
    - kbrebanov.squid
```

License
-------

BSD

Author Information
------------------

Kevin Brebanov
