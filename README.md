# git-deploy

## playbook example

``` yaml
---
- name: system
  hosts: all
  roles:
    - name: app1
      role: git-deploy
      become: yes
      vars:
        git_deploy_dir: /app/app1
        git_deploy_group:
          name: app1
        git_deploy_user:
          name: app1
          shell: /bin/sh
          comment: app1
          group: app1
          home_mode: '0700'
          password: '*'
        git_deploy_repositories:
          - repo1
          - repo2
        git_deploy_authorized_keys:
          - "ssh-rsa 123... user"
```
