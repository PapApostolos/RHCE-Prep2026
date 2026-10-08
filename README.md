# RHCE-Prep2026

## Ansible-Navigator

### Ansible-Doc
* ansible-doc
* ansible-config dump/list/view
* ansible-config --type=keyword --list
* ansible-config --type=keyword loop/vars/become

### VAULT
* ansible-vault
* ansible-vault encrypt_string --name pswdStuD3nt123
* ansible-vault encrypt secret1.yml secret2.yml --output=output-file
* ansible-vault encrypt_string --name=password_str --vault-password-file=../../.vault-password "redhat123"

---

### Ansible Run
* ansible-navigator
* ansible-navigator -m stdout
* ansible-navigator -m stdout --check
* ansible-navigator -m stdout --syntax-check
* ansible-navigator run -m stdout --syntax-check
* ansible-navigator run -m stdout --check
* ansible-navigator config dump -m stdout

### Inspect
* ansible-navigator run playbook.yml --list-tasks
* ansible-navigator run playbook.yml --list-hosts -e my_hosts='all:!servera'
* ansible-navigator run playbook.yml --list-tasks

---


### Host Pattern
anmck run playbooks/ping/host_patterns.yml
* --limit rhel-server1
* --extra my_host="all:!rhel-server2"
* --extra my_host="rhel-server1:rhel-server2"
* --extra my_host="rhel-server1:!rhel-server3"
* --extra my_host='RHEL-SERVERS:&MIRROR-SERVERS'
* --extra my_host='RHEL-SERVERS:!MIRROR-SERVERS'

---

## Git

### Git config

At **.gitconfig** file
```
git config --global user.name 'Peter Shadowman'
git config --global user.email peter@host.example.com
```

### Shell prompt

At **~/.bashrc** file:
```
source /usr/share/git-core/contrib/completion/git-prompt.sh
export GIT_PS1_SHOWDIRTYSTATE=true
export GIT_PS1_SHOWUNTRACKEDFILES=true
export PS1='[\u@\h \W$(declare -F __git_ps1 &>/dev/null && __git_ps1 " (%s)")]\$ '
```

---

