[![Build Status](https://travis-ci.org/FlorianKempenich/ansible-role-docker.svg?branch=master)](https://travis-ci.org/FlorianKempenich/ansible-role-docker) [![Ansible Role](https://img.shields.io/ansible/role/22817.svg)](https://galaxy.ansible.com/FlorianKempenich/docker)

# Ansible role: `erlang-elixir-phoenix`
Install **Erlang**, **Elixir**, and the **Phoenix Framework** on Ubuntu/Debian and OSX.

## Requirements
None

## Role Variables
For the Ubuntu installation, the Debian repo package for **Erlang** needs to be downloaded.
It is possible to set the location of the temp folder, as well as the specific version of the repo package to fetch.
Both these parameters are optional.

* `erlang_repo_temp_dir`: Optional - Default: "{{ ansible_env.HOME }}/erlang_repo_temp_dir"
* `erlang_repo_package`: Optional - Default: "erlang-solutions_1.0_all.deb"

**The temp folder will be ERASED, DO NOT PASS AN EXISTING DIRECTORY!!!**

## Example Playbook
```
- hosts: sandbox
  roles:
      - FlorianKempenich.erlang-elixir-phoenix
```

## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
