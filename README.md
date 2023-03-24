## Setup

```shell
➜ ansible-playbook --version
ansible-playbook [core 2.14.3]
  config file = /Users/rfelix/.ansible.cfg
  configured module search path = ['/Users/rfelix/.ansible/plugins/modules', '/usr/share/ansible/plugins/modules']
  ansible python module location = /usr/local/Cellar/ansible/7.3.0/libexec/lib/python3.11/site-packages/ansible
  ansible collection location = /Users/rfelix/.ansible/collections:/usr/share/ansible/collections
  executable location = /usr/local/bin/ansible-playbook
  python version = 3.11.2 (main, Feb 16 2023, 03:07:35) [Clang 14.0.0 (clang-1400.0.29.202)] (/usr/local/Cellar/ansible/7.3.0/libexec/bin/python3.11)
  jinja version = 3.1.2
  libyaml = True
```

## Basic Hello 

```shell
➜ ansible-playbook playbook.yml
```

## Hello with Var's

```shell
➜ ansible-playbook playbook.yml -e @./renato_vars.yml
```

