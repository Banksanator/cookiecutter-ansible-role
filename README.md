# Cookiecutter Ansible Role

This cookiecutter generates an [ansible role](https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html).

- [Getting Started](#getting-started)
- [Prerequisities](#prerequisities)
- [Usage](#usage)
- [Testing](#testing)

## Getting Started
These instructions will get you an Ansible Role generated using [Cookiecutter](https://github.com/cookiecutter/cookiecutter). 

This cookiecutter:
* Follows the best practices 
* Asks you if some features are wanted or not in the role
* Generates a Pipfile and Pipfile.lock for using the role based on some parameters

### Prerequisities

You just need to have [pipenv](https://github.com/pypa/pipenv) installed.

## Usage

To generate your ansible role type ```printf "cookiecutter==1.7.2\nJinja2==2.11.2" > requirements.txt && pipenv install -r requirements.txt && pipenv run cookiecutter https://github.com/Banksanator/cookiecutter-ansible-role/tree/develop && rm -rf Pipfile*
requirements.txt && pipenv --rm && rm -rf requirements.txt```.

Then, introduce some parameters needed for generating it. 

It displays some comments that help you to use the cookiecutter sucessfully, if you assign value to them nothing happens.

```
  "comment_0":"The role name will be the value you assign to app_name with _role appended",
  "comment_1":"Introduce in exec_name the executable file name, you can change it later in the defaults/main.yml if you don't know it",
  "app_name": "",
  "exec_name":"",
  "github_user": "Enter Gitlab Username:",
  "company": "Ex. HEB",
  "author": "Enter Name:",
  "min_ansible_version": "",
  "ansible_version": "5.2.0",
  "molecule_version": "3.4.0",
  "python_docker_version": "5.0.0",
  "molecule_docker_version": "0.2.4",
  "ansible_lint_version":"5.3.2",
  "yamllint_version": "1.28.0",
  "license":"Apache 2.0",
  "galaxy_tag_1":"tag1",
  "galaxy_tag_2":"tag2",
  "galaxy_tag_3":"tag3",
  "debian_bullseye_support":["True", "False"],
  "debian_buster_support":["True", "False"],
  "has_service":["True", "False"],
  "has_files":["True", "False"],
  "comment_2":"If there is service the following options will not have any effect",
  "has_handlers":["True", "False"],
  "has_templates":["True", "False"],
  "documentation_URL":""
```

It will create the following file structure:

```
github_cli_role
├── CHANGELOG.md
├── defaults
│   └── main.yml
├── files
├── handlers
│   └── main.yml
├── LICENSE
├── logo.gif
├── meta
│   └── main.yml
├── molecule
│   └── default
│       ├── converge.yml
│       ├── Dockerfile.j2
│       ├── molecule.yml
│       ├── tests
│       │   └── test_app.yml
│       └── verify.yml
├── Pipfile
├── Pipfile.lock
├── README.md
├── tasks
│   ├── config.yml
│   ├── install.yml
│   ├── main.yml
│   └── service.yml
├── templates
│   └── github_cli.service.j2
└── test-requirements.txt
```

## Testing 

Test the cookiecutter just by typing:

```./test.sh```
