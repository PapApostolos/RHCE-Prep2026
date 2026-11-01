# RHCE

Notes and comments for RHCE exam.
Contents:
- [VSCode IDE](#vscode-ide)
- [Git](#git)
- [Add-Hoc Commands](#add-hoc-commands)
- [Ansible-Config](#ansible-config)
- [Ansible-Navigator](#ansible-navigator)
- [Inventory](#inventory)


## VSCode IDE


### Shortcuts

- `Ctrl + ,` --> Settings
- `Ctrl+Shift+G` keyboard.com -> Source Control view in the Side Bar



### Set DevContainer

1. Configure VSCode Extentions:
	- Dev Containers
		- `Dev › Containers: Docker Compose Path` -> `podman-compose`
		- `Dev › Containers: Docker Path` -> podman
	- Ansible extention
		- `Ansible > Validation > Lint:Enabled`
		- `Ansible > Execution Environment: Enabled`

![[Pasted image 20261024231113.png]]


2. At sidebar `Ansible `> `Create a dev container`
	- Select: Container image --> `Downstream (registry.redhat.io/ansible-automation-...`)
	- Click: `Create`

![[Pasted image 20261024231032.png]]

3. Update `podman/devcontainer.json` settings of the .development `image key`:
	- `my-registry.com/user/ansible-dev-tools-rhel9:latest`
	- `registry.redhat.io/ansible-automation-platform-26/ansible-dev-tools-rhel9`
4. After you create an Ansible Playbook in your project, you can use automation content navigator to run the playbook in the development container.
	- Right-click your playbook in the file explorer
	- Run Ansible Playbook Via…​ → Run playbook via 'ansible-navigator run'.




![[Pasted image 20261025002149.png]]

Other Extentions:
- Syntax highlighting
- Source Control Integration
- Code completion (InteliSence)




## Git

***Git-Config***:
- `git config --global user.name 'Peter Shadowman'
- `git config --global user.email peter@host.example.com`



## Ansible-Config

***ansible-config***
- ansible-config { list / view / init }
- ansible-config init --disable > ansible.cfg.tst
- ansible-config dump --only-changed

ansible.cfg
`
```
[defautl]
ask_pass=false
remote_user=ans-user
inventory=/path/to/inventoy

[privilege_escalation]
become=false
become_user=root
become_method=sudo
become_ask_pass=false
```

## Add Hoc Commands

Simple terminal commands that can be used during linux

- ansible LOCAL_SERVERS -m service_facts | less -I
- ansible LOCAL_SERVERS -m systemd_service -a "name=firewalld" --check | less -I


## Ansible-Navigator


Execution-Environment
```
podman login registry.redhat.io
registry.redhat.io/ansible-automation-platform-26/ee-supported-rhel9

ansible-navigator images \
--eei registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9 \
--pp missing --tls-verify=false --pae false --mode stdout
```

**Debug Process:**
	* anm run play.yml --list-tasks
	* anm run play.yml --start-at-task "taskName"
	* anm run play.yml --step # step-by-step execution


**Logs**
```
$ANSIBLE_LOG_PATH
ansible.cfg
[defaults]
log_path=/path/to/file

ansible-navigator.yml
ansible-navigator:
	playbook-artifacts:
		enaible: false
```
*Commands (alias anm='ansible-navigator -m stdout')*


## Ansible-Inventory

***ansible-inventory***

- inventory
	- group_vars
	- hosts_vars
### Git



### Git