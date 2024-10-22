# Ansible Role: AWX (open source Ansible Tower)
![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

> **DEPRECATED**: This role has been deprecated. AWX installation is a lot different than it was when I first created the role, and continues evolving. Please follow the official install guide and if you need automation around it, please consider the [awx-operator](https://github.com/ansible/awx-operator).

Installs and configures [AWX](https://github.com/ansible/awx), the open source version of [Ansible Tower](https://www.ansible.com/tower).

## Requirements

Before this role runs, assuming you want the role to completely set up AWX using it's included installer, you need to make sure the following AWX dependencies are installed:

| Dependency                    | Suggested Role           |
| ----------------------------- | ------------------------ |
| EPEL repo (RedHat OSes only)  | `nholuong.repo-epel`  |
| Git                           | `nholuong.git`        |
| Ansible                       | `nholuong.ansible`    |
| Docker                        | `nholuong.docker`     |
| Python Pip                    | `nholuong.pip`        |
| Node.js (10.x)                | `nholuong.nodejs`     |

See this role's [`molecule/default/converge.yml`](molecule/default/converge.yml) playbook for an example that works across many different OSes.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):

    awx_repo: https://github.com/ansible/awx.git
    awx_repo_dir: "~/awx"
    awx_version: devel
    awx_keep_updated: true

Variables to control what version of AWX is checked out and installed.

    awx_run_install_playbook: true

By default, this role will run the installation playbook included with AWX (which builds a set of containers and runs them). You can disable the playbook run by setting this variable to `false`.

## Dependencies

None.

## Example Playbook

```yaml
- hosts: awx-centos
  become: true

  vars:
    nodejs_version: "10.x"
    docker_install_compose: false
    pip_install_packages:
      - name: docker
      - name: docker-compose

  roles:
    - nholuong.repo-epel
    - nholuong.git
    - nholuong.pip
    - nholuong.ansible
    - nholuong.docker
    - nholuong.nodejs
    - nholuong.awx
```

After AWX is installed, you can log in with the default username `admin` and password `password`.

# 🚀 I'm are always open to your feedback.  Please contact as bellow information:
### [Contact ]
* [Name: nho Luong]
* [Skype](luongutnho_skype)
* [Github](https://github.com/nholuongut/)
* [Linkedin](https://www.linkedin.com/in/nholuong/)
* [Email Address](luongutnho@hotmail.com)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License
* Nho Luong (c). All Rights Reserved.🌟
