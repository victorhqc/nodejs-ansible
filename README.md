# nodejs-ansible
My personal node.js ansible deployment playbooks.

## Introduction

This repository is meant to be to make Node.js applications easy to deploy and
update in your server. I created it because I always do this manually and it can
be troublesome or repetitive.

## Requirements

+ Your own server up and running.
+ Have SSH Enabled with a sudo user already enabled.
+ Ansible
+ Linux server

## How to use

There are some playbooks preconfigured here:

+ firstrun_example.yml
+ groups/configure_example.com.yml
+ groups/update_example.com.yml

Duplicate each, rename it to match your own domain and tweak the settings.

### Firstrun

This playbook should run only once per server! As it creates a new user and
creates a new SSH key to it.

```sh
cd automation
ansible-playbook playbooks/firstrun_example.com.yml
```

### Configure

This playbook is for deploying the Node.js project for the very first time. It installs
Node.js, downloads dependencies, configures Nginx and sets it up and running.

```sh
cd automation
ansible-playbook playbooks/configure_example.com.yml
```

### Update

This playbook should run regularly. Whenever you have a new version of your application.

```sh
cd automation
ansible-playbook playbooks/update_example.com.yml
```
