[![Build Status](https://travis-ci.org/TOOCS/elixir.svg?branch=master)](https://travis-ci.org/TOOCS/elixir) [![Ansible Role](https://img.shields.io/ansible/role/36108.svg)](https://galaxy.ansible.com/FlorianKempenich/toocs_elixir)


# TOOCS / Ansible Role: `FlorianKempenich.toocs_elixir`
> #### /!\ This role has been renamed - Old name: `erlang-elixir-phoenix` /!\

Install **Erlang**, **Elixir**, and the **Phoenix Framework** on Ubuntu/Debian and OSX.

> ### TOOCS?
> TOOCS - The Opinionated One-Click Setups are a set of tools / ansible roles designed to setup a system in one click. They are a simple, reliable, way to setup a given tool. You can use them as is, or, inspecting their code, as a tutorial to follow step by step.
>
> They are, as their name suggests, opinionated: while they guarantee to setup the given tool in one click, they do **not** guarantee consistency in _how_ they achieve it, new releases might introduce breaking changes.
> Read the code and make sure you understand what's happening!

## Requirements
None

## Role Variables
For the Ubuntu installation, the Debian repo package for **Erlang** needs to be downloaded.
It is possible to set the location of the temp folder, as well as the specific version of the repo package to fetch.
Both these parameters are optional.

* `erlang_repo_temp_dir`: Optional - Default: `"{{ ansible_env.HOME }}/erlang_repo_temp_dir"`
* `erlang_repo_package`: Optional - Default: `"erlang-solutions_1.0_all.deb"`

**The temp folder will be ERASED, DO NOT PASS AN EXISTING DIRECTORY!!!**

## Example Playbook
```
- hosts: sandbox
  roles:
      - FlorianKempenich.toocs_elixir
```

## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
