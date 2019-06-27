Role Name
=========
```
role_git-repo_setting
ROLE_ID: '0x01'
```
Requirements
------------
```
Packages on control nodes:
- git 
- ansible
```

Role Variables
--------------
```
folder_create_force: boolen . 
github_username: string  
github_password: string . 
repo_folder_path_in_role: dict. list  
repo_folder_path_n_in_role: dict. list . 
git_configuration: dict. list . 

```
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
    - role: role_git-repo_setting
      github_username: ''
      github_password: ''
      repo_folder_path_in_role:
        - path: /home/{{ ansible_user }}/git/repo01
          remote_sync: false
          url: 'https://github.com/owner/yourRepoName01.git' 
          git_clone: none
          version: master
      repo_folder_path_n_in_role:
        - path: /home/{{ ansible_user }}/git/repo01
          remote_sync: false
          url: 'https://github.com/owner/yourRepoName02.git' 
          git_clone: none
          version: master
      git_configuration:
        - name: 'user.name'
          scope: global
          value: "{{ ansible_user }}"
        - name: 'user.email'
          scope: global
          value: "{{ ansible_user }}@{{ inventory_hostname }}"
```    

Tags
-------
```
- environment_verify
    - check_repo_path_existed
    - pre_check_git_config
- role_init
- git_init
    - git_configure
    - git_initialize
```

License
-------

BSD

Author Information
------------------

Jack Liu
