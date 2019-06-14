# ansible-from-tasks-to-roles

This is a project accompanying a blog post on Ansible's Roles feature - https://blog.tratif.com/2018/06/04/ansible-from-tasks-to-roles/.

### Requirements

OS: `CentOS 7`

Vagrant: `2.0.4`

Ansible: `2.3.0.0`

### Usage

The project holds several subprojects. Each subsequent folder being an improvement of previous subproject, e.g. `02` is an improvement of `01`.

Check the `inventory` files to re-configure connectivity details, if needed.

Running subprojects:
```
$ cd <subproject_folder>/
$ ansible-playbook deploy/play.yml -i inventory
```

Subproject `03` has a vault file, so you need to enter vault password:
```
$ cd 03/
$ ansible-playbook deploy/play.yml -i inventory --ask-vault-pass
Vault password: ...
```

Vault password used in this project: "vault" (without quotes)

Keep the password safe in your production projects!

### Other info

To create a self-signed certificate, use the below command:
```
openssl req -x509 -newkey rsa:4096 -nodes -keyout nginx.key -out nginx.crt -days 3650
```
