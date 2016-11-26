Ansible Role Nginx Upstream
======================================

Ansible role to configure nginx upstreams used for loadbalancing.

Requirements
------------

None.

Role Variables
--------------

- `nginx_user`:
Name of system user to run service with. Default value is "nginx"

- `nginx_group`:
Name of system group to run service with. Default value is "nginx"

- `nginx_services`:
Array with services to be restarted on configuration changes. Default value
is ["nginx"]

- `nginx_upstreams`:
Array with upstream configuration. See [default vars file](defaults/main.yml)


Dependencies
------------

None.

Example Playbook
----------------
```
- hosts: all
  roles:
    - role: vundb-nginx-lb
      nginx_upstreams:
        - label: "example-com"
          server_name: "example.com"
          port: 80
          ip_hash: true
          keepalive: 32
          servers:
            - "127.0.0.1:81"
```

License
-------

MIT

Author Information
------------------

- You can find more roles in my GitHub channel [vundb](https://github.com/vundb)
- Follow me on Twitter [@vundb](https://twitter.com/vundb)
