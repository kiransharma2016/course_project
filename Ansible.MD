## useful snippets
https://awsbloglink.wordpress.com/2017/11/05/how-to-restart-the-os-with-ansible/

## how to run playbook on localhost
There are two ways to provide hosts in ansible
--command to use an inline inventory list, eg -c local -i 'localhost,' playbook \
--put all your host in a file and give that with -i inventory file with location while running the playbook
eg

ansible-playbook -c local -i 'localhost,' playbook.yaml

## comments a line when not commented. 
#### This comments swap line in fstab and also turn off swap 
---
- name: Test \
  hosts: all \
  gather_facts: false \
  become: true \
  tasks: \
    - name: Comment out pipeline archive in fstab \
      command: sed -i.bak '/^#/! s/^\(.*swap.*\)/#\1/g' /etc/fstab 

      args: \
        warn: false # set warn=false to prevent warning \
      register: services_list

    - name: Disable swap \
      command: swapoff -a \
      when: ansible_swaptotal_mb > 0

## selinux disabling and making it permissive 
# tasks for disabling selinux
- name: Install prerquisite lib for Selinux Ansible module \
  yum: \
    name: "{{item}}" \
    state: latest \
  with_items: \
    - libselinux-python \
    - libsemanage-python 

- name: Disabling Selinux -- this will be implemented in the next reboot \
  selinux: \
    state: disabled 

- name: Setting  SeLinux mode to permissive until the server gets rebooted  \
  command: setenforce 0 \
  ignore_errors: true \
  changed_when: false 


## misc
 swapon --all \
 swapon -s
 
