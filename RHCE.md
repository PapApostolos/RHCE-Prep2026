
## Pre-Start

.devcontainer:
 -  "image": "ghcr.io/ansible/community-ansible-dev-tools:latest",

podman images:
- localhost/apap/ibm/ee-test1                                           v1.0
- localhost/ee-test1                                                    v1
- registry.redhat.io/ansible-automation-platform-27/ee-supported-rhel9  latest
- registry.redhat.io/ansible-automation-platform-26/ee-minimal-rhel9    latest
- ghcr.io/ansible/community-ansible-dev-tools                           latest
- registry.redhat.io/ubi8/ubi                                           latest


alias ad="ansible-doc";
alias ac="ansible-config";
alias ai="ansible-inventory";
alias an="ansible-navigator"; alias anm="ansible-navigator -m stdout";
alias anck="ansible-navigator -m stdout --check";
alias ansck="ansible-navigator -m stdout --sytanx-check";
export ansible_config="/mnt/c/users/apostolospapatheodor/desktop/redhat/rhce/prep-win1/ansible.cfg";
export ANSIBLE_CONFIG="/mnt/c/Users/ApostolosPapatheodor/Desktop/RedHat/RHCE/RHCE-Prep2026/prep1/ansible.cfg";
