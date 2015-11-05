# Ansible Cookbook for Rails Development Environment

## What is this?

This repository contains playbook for RubyOnRails development environment. This playbook contains below.

- rbenv
- git (ver. 2.x)
- bundler
- mysql (or postgresql)

## How to setup?

### 1. install VirtualBox

https://www.virtualbox.org/

### 2. install vagrant

https://www.vagrantup.com/

### 3. install ansible

```
$ brew install ansible
```

### 4. vagrant up

```
$ git clone git@github.com:hirota-inoue/ansible-cookbook-rails-dev.git rails-dev
$ cd rails-dev
$ vagrant up
```

### 5. start development

good luck!
