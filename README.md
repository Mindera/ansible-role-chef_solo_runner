Ansible Role: Chef Solo runner
=========

Runs chef-solo giving the cookbooks archive, the json attributes (usually called node.json) file 
and optionaly the location of databags, environments and roles.

Giving a Chef run list, roles, environments and attributes, this role runs Chef Solo in the targets machines.
It packages all the dependencies cookbooks using berkshelf, copy them to the target, unpack them, and run chef-solo.

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

    - hosts: servers
      roles:
         - role: chef_solo_runner
           chef_solo_runner_cookbook_archive_file: "cookbooks.tar.gz"
           chef_solo_runner_node_json_file: "node.json"

License
-------

MIT
