repository_setup
================

This role allows setting up a new file repository.

#### Parameters:
- name (M) - name of repository
- port (M) - public TCP port for accessing the repository files
- security (O) - a dictionary with values specifying repository's security details; see below:
```
security:
  ssl: yes|no
  basic_auth:
    user: 'username'
    password: 'some_password'
```
By ommiting dictionary values, you can choose security configuration:
- only SSL
- only Basic Auth
- SSL + Basic Auth

##### Legend:
- (M) - specifies mandatory parameters
- (O) - specifies optional parameters

#### Invocation:
- in playbooks:
```
- hosts: ...
  roles:
    - { role: repository_setup,
        name: "repository1",
        port: "8080"
      }
    - { role: repository_setup,
        name: "repository2",
        port: "8081",
        security: {
          ssl: yes
        }
      }
```
(repository1 does not have SSL nor Basic Auth security)
- in other roles:
```
- include_role:
    name: repository_setup
  vars:
    name: "repository3"
    port: "8082"
    security:
      ssl: yes
      basic_auth:
        user: "user1"
        password: "some_pwd"
```
