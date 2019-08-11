golang
======

Install and configure Go on Fedora.

Role Variables
--------------

|name|description|type|default|
|go_111_module|Enable Go 1.11 modules|One of [auto, on, off]|auto|
|go_install_packages|A list of Go packages to install|list|[]|
|go_user_gopath|User's GOPATH|string|"{{ ansible_user_dir }}/go"|
|go_os_output_gopath|If set to 1, create an isolated GOPATH inside \_output using symlinks to avoid other packages being accidentally included|bool|1|

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  tasks:
  - import_role:
      name: golang
    vars:
      go_111_module: auto
      go_user_gopath: "{{ ansible_user_dir }}/go"
      go_os_output_path: 1
      go_install_packages:
        - github.com/derekparker/delve/cmd/dlv
```

License
-------

MIT