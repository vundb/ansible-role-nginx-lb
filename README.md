Ansible Role Nginx Lb
======================================

This role will configure running nginx instance as loadbalancer.

Requirements
------------

None.

Role Variables
--------------

None.

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
