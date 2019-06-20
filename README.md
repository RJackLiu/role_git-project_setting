Role Name
=========

role_git-project_setting
ROLE_ID: '0x01'

Requirements
------------

Packages on control nodes:
- git 
- ansible


Role Variables
--------------

folder_create_force: boolen . 
github_username: string  
github_password: string . 
project_folder_path_in_role: dict. list  
project_folder_path_n_in_role: dict. list . 
git_configuration: dict. list . 


Dependencies
------------

none

Example Playbook
----------------
```    
---
- hosts: all
  gather_facts: no
  become: no
  roles:
    - role: role_git-project_setting
      github_username: ''
      github_password: ''
      project_folder_path_n_in_role:
        - path: /home/{{ ansible_user }}/git/project01
          remote_sync: false
          url: 'https://github.com/owner/yourPojectName02.git' 
          git_clone: true
      project_folder_path_n_in_role:
        - path: /home/{{ ansible_user }}/git/project01
          remote_sync: false
          url: 'https://github.com/owner/yourPojectName02.git' 
          git_clone: true
      git_configuration:
        - name: 'user.name'
          scope: global
          value: "{{ ansible_user }}"
        - name: 'user.email'
          scope: global
          value: "{{ ansible_user }}@{{ inventory_hostname }}"
```        
License
-------

BSD

Author Information
------------------

Jack Liu
