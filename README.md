[![Build Status](https://travis-ci.org/TOOCS/elixir.svg?branch=master)](https://travis-ci.org/TOOCS/elixir) [![Ansible Role](https://img.shields.io/ansible/role/36202.svg)](https://galaxy.ansible.com/TOOCS/elixir)


# TOOCS / Ansible Role: `TOOCS.elixir`
> #### /!\ This role has been renamed - Old name: `FlorianKempenich.erlang-elixir-phoenix` /!\

Install **Erlang**, **Elixir**, and the **Phoenix Framework** on Ubuntu/Debian and OSX.

> ### TOOCS?
> TOOCS - The Opinionated One-Click Setups are a set of tools / ansible roles designed to setup a system in one click. They are a simple, reliable, way to setup a given tool. You can use them as is, or, inspecting their code, as a tutorial to follow step by step.
>
> They are, as their name suggests, opinionated: while they guarantee to setup the given tool in one click, they do **not** guarantee consistency in _how_ they achieve it, new releases might introduce breaking changes.
> Read the code and make sure you understand what's happening!

## Requirements
This role is only working on MacOSX & Ubuntu/Debian.

## Role Variables

* ### `erlang_versions`
  * List of erlang versions to install with `asdf`
  * The first from the list will be set as `global` (default)
  * Only used with `asdf` installation method, `native` method will install the latest available version
  * For more info on which version to use, see [TOOCS.asdf - Supported Languages](https://github.com/TOOCS/asdf#supported-languages)
  * **Default:** `[20.3.8.9]`

* ### `elixir_versions`
  * List of elixir version to install with `asdf`
  * The first from the list will be set as `global` (default)
  * `elixir` requires `erlang` to be installed
  * Only used with `asdf` installation method, `native` method will install the latest available version
  * For more info on which version to use, see [TOOCS.asdf - Supported Languages](https://github.com/TOOCS/asdf#supported-languages)
  * **Default:** `[1.7.4]`

* ### `installation_method`
  * Valid values: `asdf`, `native`
  * See [Installation Methods](#installation-methods)
  * **Default:** `asdf`

* ### `asdf_skip_shell_setup`
  * Skip the shell setup when installing `asdf`
  * See [Installation Methods](#installation-methods)
  * **Default:** `false`

* ### `erlang_repo_package`
  * Erlange repo package to use when installing with `native` method
  * **Default:** `erlang-solutions_1.0_all.deb`

## Installation Methods
* ### `asdf`
  Prefered and default installation method using the `asdf` version manager
  
  The installation and configuration of `asdf` as well as the erlang/elixir installation is delegated to another TOOCS: [TOOCS.asdf](https://github.com/TOOCS/asdf).

  **Note:** Erlang and Elixir being compiled from source, it is normal for the setup to hang on the installation steps.
  
  #### Post install - with `asdf`: Shell configuration
  * **If you are using `zsh`, you're all set!** Your shell has been automatically set up during the installation of `asdf`.
  
  * **If you are NOT using `zsh` some manual setup is required, see:** [TOOCS/asdf - Non `zsh` Users](https://github.com/TOOCS/asdf#non-zsh-users)
  
  * Alternatively, if `asdf` is already setup on your machine, you might want to skip the `asdf` automatic shell setup => Set the variable `asdf_skip_shell_setup` to `true`

* ### `native`
  Alternative version using installing erlang/elixir as native packages, using `apt` or `homebrew`.

## Example Playbook
```yaml
- hosts: localhost
  tasks:
    - include_role:
        name: TOOCS.elixir

# OR

- hosts: localhost
  tasks:
    - include_role:
        name: TOOCS.elixir
      vars:
        erlang_versions:
          - 20.3.8.9
          - 21.1.4
        elixir_versions:
          - 1.7.4
          - 1.6.6

# OR

- hosts: localhost
  tasks:
    - include_role:
        name: TOOCS.elixir
      vars:
        installation_method: "native"
```

## License
MIT

## Author Information
Find out more about my work: [Florian Kempenich](https://floriankempenich.com)
