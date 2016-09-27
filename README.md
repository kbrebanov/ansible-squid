squid
=====

[![Build Status](https://travis-ci.org/kbrebanov/ansible-squid.svg?branch=master)](https://travis-ci.org/kbrebanov/ansible-squid)

Installs Squid

Requirements
------------

This role requires Ansible 1.9 or higher.

Role Variables
--------------

| Name                                | Default                                                     | Description                                                                                            |
|:------------------------------------|:------------------------------------------------------------|:-------------------------------------------------------------------------------------------------------|
| squid_access_log                    | "daemon:/var/log/{{ squid_service_name }}/access.log squid" | Configures whether and how Squid logs HTTP and ICP transactions                                        |
| squid_acls                          | []                                                          | List of ACL hashes (keys: name, type, argument)                                                        |
| squid_always_directs                | []                                                          | List of always_direct options (keys: type, acl_name)                                                   |
| squid_cache_peers                   | []                                                          | List of cache peers (keys: hostname, type, http_port, icp_port, options<list>)                         |
| squid_dns_v4_first                  | "off"                                                       | This option reverses the order of preference to make Squid contact dual-stack websites over IPv4 first |
| squid_forwarded_for                 | "on"                                                        | Set X-Forwarded-For header in HTTP requests                                                            |
| squid_http_access_allow_clients     | ["localhost"]                                               | List of clients to allow access                                                                        |
| squid_http_port                     | 3128                                                        | The port where Squid will listen for HTTP requests                                                     |
| squid_httpd_suppress_version_string | "off"                                                       | Suppress Squid version string info in HTTP headers and HTML error pages                                |
| squid_netdb_filename                | "stdio:stdio:/var/log/{{ squid_service_name }}/netdb.state" | Where Squid stores it's netdb journal                                                                  |
| squid_never_directs                 | []                                                          | List of never_direct options (keys: type, acl_name)                                                    |
| squid_pinger_enable                 | "on"                                                        | Control whether the pinger is active at run-time                                                       |
| squid_proxy_only                    | false                                                       | If enabled, disables caching                                                                           |
| squid_tcp_outgoing_address          | ''                                                          | Map requests to different outgoing IP address                                                          |
| squid_via                           | "on"                                                        | If set (default), Squid will include a Via header in requests and replies are required by RFC2616      |
| squid_visible_hostname              | ''                                                          | If you want to present a special hostname in error messages, etc, define this                          |

Dependencies
------------

None

Example Playbook
----------------

Install Squid
```yaml
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
