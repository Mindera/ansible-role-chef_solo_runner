Ansible Role: Chef Solo runner
=========

[![Ansible-Galaxy][ansible-image]][ansible-link]

[ansible-image]: https://img.shields.io/badge/ansible--galaxy-1.1.0-brightgreen.svg
[ansible-link]: https://galaxy.ansible.com/list#/roles/3573

Runs chef-solo giving the cookbooks archive, the json attributes file (usually called node.json)
and optionaly the location of databags, environments and roles.

It copies all the needed chef materials to a location on the target machine ('/var/tmp/chef-solo' by default) and then
executes chef-solo. Chef logs are dumped in '/var/log/chef-solo.log' by default.

Requirements
------------

Chef-solo installed in the target machines.

Role Variables:
--------------

- chef_solo_runner_cookbook_archive_file
- chef_solo_runner_node_json_file
- chef_solo_runner_environment (optional)
- chef_solo_runner_environments_dir (optional)
- chef_solo_runner_data_bags_dir (optional)
- chef_solo_runner_roles_dir (optional)
- chef_solo_runner_encrypted_data_bag_secret_file (optional)
- chef_solo_runner_solo_path (default: "/var/tmp/chef-solo")
- chef_solo_runner_solo_log (default: "/var/log/chef-solo.log")
- chef_solo_runner_solo_log_level (default: "info")
- chef_solo_runner_destroy_solo_materials (default: false)

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: servers
  roles:
     - role: chef_solo_runner
       chef_solo_runner_cookbook_archive_file: "cookbooks.tar.gz"
       chef_solo_runner_node_json_file: "node.json"
```

License
-------

MIT
