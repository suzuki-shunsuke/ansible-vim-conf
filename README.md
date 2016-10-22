vim-conf
=========

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-vim-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-vim-conf)

Install your vim config hosted on the Github.

Requirements
------------

* [motemen/ghq](https://github.com/motemen/ghq)

The directory structure of the repository where your vim config is hosted must be in the following manner.

```
(repository root)/
  .vimrc
  .vim
```

Role Variables
--------------

* vim_conf_ghq_executable: The executable path of ghq command. The default is "ghq".
* remote_repository_path: The remote repository where your vim config is hosted.

Dependencies
------------

* [suzuki-shunsuke.ghq-module](https://galaxy.ansible.com/suzuki-shunsuke/ghq-module/)

Example Playbook
----------------

```yaml
- hosts: servers
  vars:
    vim_conf_ghq_executable: /home/vagrant/.go/bin/ghq
  roles:
  - role: suzuki-shunsuke.vim-conf
    remote_repository_path: suzuki-shunsuke/vim.conf
```

License
-------

MIT
