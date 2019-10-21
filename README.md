ansible-role-linux-ad-manage
=========

A role to manage ad for a computer. At present the only action (`active_directory_command`) is `join`. Other commands will come later/

Role Variables
--------------
```yaml
active_directory_command: join
ad_manage_dns_name: example.com
ad_manage_domain_join_user: Administrator
ad_manage_domain_ou_path: "OU=example,DC=example,DC=com"
ad_manage_domain_join_user:
ad_manage_domain_join_pass:
```


Example Playbook
----------------

```yaml
---
- name: Join to AD
  hosts: "{{ short_hostname }}.example.com"
  roles:
    - role: ansible-role-linux-ad-manage
      vars:
        ad_manage_dns_name: dc
        ad_manage_domain_join_user: "Administrator@dc"
        ad_manage_domain_join_pass: password
        ad_manage_domain_ou_path: "OU=example,DC=example,DC=com"
        active_directory_command: join
```

License
-------

MIT
