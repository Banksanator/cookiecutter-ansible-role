
This role has been generated using the [cookiecutter](https://github.com/cookiecutter/cookiecutter) tool.

- [Getting Started](#getting-started)
	- [Prerequisities](#prerequisities)
	- [Installing](#installing)
- [Usage](#usage)
- [Testing](#testing)


## Getting Started
These instructions will get you a copy of the role for your Ansible playbook. Once launched, it will install {{ cookiecutter.app_name | replace('_',' ') | title }} in a Debian system.

### Prerequisities

Ansible {{ cookiecutter.ansible_version }} version installed.

Molecule 3.x.x version installed.

For testing purposes, [Molecule](https://molecule.readthedocs.io/) with [Docker](https://www.docker.com/) as driver and [Goss](https://github.com/aelsabbahy/goss) as verifier.

### Installing

Create or add to your roles dependency file (e.g requirements.yml):

```
- src: HEB.{{ cookiecutter.app_name }}_role
  version: 1.0.0
  name: {{ cookiecutter.app_name }}_role
```

Install the role with ansible-galaxy command:

```
ansible-galaxy install -p roles -r requirements.yml -f
```

Use in a playbook:

```
---
- hosts: someserver
  roles:
    - role: {{ cookiecutter.app_name }}_role
```

## Usage

Look to the [defaults](defaults/main.yml) properties file to see the possible configuration properties, it is very likely that you will not need to override any variables.


## Testing

### Install dependencies

```sh
$ pipenv sync
```

For more information read the [pipenv docs](ipenv-fork.readthedocs.io/en/latest/).

### Testing

```sh
$ pipenv run molecule test 
```

## Built With

![Ansible](https://img.shields.io/badge/ansible-{{ cookiecutter.ansible_version }}-green.svg)
![Molecule](https://img.shields.io/badge/molecule-{{ cookiecutter.molecule_version }}-green.svg)
![Goss](https://img.shields.io/badge/goss-0.3.16-green.svg)


