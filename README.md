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
TASK [Gathering Facts] ********************************************************************************************
Friday 24 March 2023  16:04:52 -0300 (0:00:00.014)       0:00:00.014 **********
ok: [localhost]

TASK [just execute a ls -lrt command] *************************************************************************************************************************************************************************************************
Friday 24 March 2023  16:04:53 -0300 (0:00:00.902)       0:00:00.917 **********
changed: [localhost]

TASK [output of ls] ********************************************************************************************
Friday 24 March 2023  16:04:53 -0300 (0:00:00.500)       0:00:01.417 **********
ok: [localhost] => {
    "output.stdout_lines": [
        "total 32",
        "-rw-r--r--@ 1 rfelix  staff  308 Mar 24 16:01 playbook.yml",
        "-rw-r--r--@ 1 rfelix  staff   24 Mar 24 16:01 renato_vars.yml",
        "-rw-r--r--@ 1 rfelix  staff  857 Mar 24 16:02 README.md",
        "-rw-r--r--@ 1 rfelix  staff   13 Mar 24 16:02 yelken_vars.yml"
    ]
}

TASK [Print the name] ********************************************************************************************
Friday 24 March 2023  16:04:53 -0300 (0:00:00.036)       0:00:01.454 **********
ok: [localhost] => {
    "name": "VARIABLE IS NOT DEFINED!"
}
```

## Hello with Var's

> With **Renato's**

```shell
➜ ansible-playbook playbook.yml -e @./renato_vars.yml
PLAY [Playing with Ansible and Git] ********************************************************************************************

TASK [Gathering Facts] ********************************************************************************************
Friday 24 March 2023  16:05:29 -0300 (0:00:00.013)       0:00:00.013 **********
ok: [localhost]

TASK [just execute a ls -lrt command] ********************************************************************************************
Friday 24 March 2023  16:05:30 -0300 (0:00:00.920)       0:00:00.933 **********
changed: [localhost]

TASK [output of ls] ********************************************************************************************
Friday 24 March 2023  16:05:30 -0300 (0:00:00.511)       0:00:01.445 **********
ok: [localhost] => {
    "output.stdout_lines": [
        "total 32",
        "-rw-r--r--@ 1 rfelix  staff   308 Mar 24 16:01 playbook.yml",
        "-rw-r--r--@ 1 rfelix  staff    24 Mar 24 16:01 renato_vars.yml",
        "-rw-r--r--@ 1 rfelix  staff    13 Mar 24 16:02 yelken_vars.yml",
        "-rw-r--r--@ 1 rfelix  staff  2232 Mar 24 16:05 README.md"
    ]
}

TASK [Print the name] ********************************************************************************************
Friday 24 March 2023  16:05:31 -0300 (0:00:00.038)       0:00:01.483 **********
ok: [localhost] => {
    "name": "Renato Alves Felix"
}

PLAY RECAP ********************************************************************************************
localhost                  : ok=4    changed=1    unreachable=0    failed=0    skipped=0    rescued=0    ignored=0
```

> With Yelken's

```
➜ ansible-playbook playbook.yml -e @./yelken_vars.yml
PLAY [Playing with Ansible and Git] ********************************************************************************************

TASK [Gathering Facts] ********************************************************************************************
Friday 24 March 2023  16:06:17 -0300 (0:00:00.016)       0:00:00.016 **********
ok: [localhost]

TASK [just execute a ls -lrt command] ********************************************************************************************
Friday 24 March 2023  16:06:18 -0300 (0:00:00.976)       0:00:00.992 **********
changed: [localhost]

TASK [output of ls] ********************************************************************************************
Friday 24 March 2023  16:06:18 -0300 (0:00:00.530)       0:00:01.522 **********
ok: [localhost] => {
    "output.stdout_lines": [
        "total 32",
        "-rw-r--r--@ 1 rfelix  staff   308 Mar 24 16:01 playbook.yml",
        "-rw-r--r--@ 1 rfelix  staff    24 Mar 24 16:01 renato_vars.yml",
        "-rw-r--r--@ 1 rfelix  staff    13 Mar 24 16:02 yelken_vars.yml",
        "-rw-r--r--@ 1 rfelix  staff  3868 Mar 24 16:06 README.md"
    ]
}

TASK [Print the name] ********************************************************************************************
Friday 24 March 2023  16:06:18 -0300 (0:00:00.037)       0:00:01.559 **********
ok: [localhost] => {
    "name": "Yelken"
}
```

