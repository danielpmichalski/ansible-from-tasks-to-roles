repository_files_setup
======================

This role allows creating repository files.

Parameters:
- name - name of repository in which files are to be created
- files - a list of file tupples; each file tupple requires 'name' and 'content' attributes (see below example)

Invocation:
- in playbooks:
```
- hosts: ...
  roles:
    - { role: repository_files_setup, name: repository1, files: "{{ vars_files }}" }
```
- in other roles:
```
- include_role:
    name: repository_files_setup
  vars:
    name: repository1
    files:
      -
        name: file1
        content: "some content..."
      -
        name: file2
        content: "some content2..."
```
