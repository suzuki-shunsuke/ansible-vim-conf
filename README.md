# ansible-vim-conf

[![Build Status](https://travis-ci.org/suzuki-shunsuke/ansible-vim-conf.svg?branch=master)](https://travis-ci.org/suzuki-shunsuke/ansible-vim-conf)

ansible role to install vim configurations hosted on the Github.

https://galaxy.ansible.com/suzuki-shunsuke/vim-conf/

## Requirements

The directory structure of the repository where your vim config is hosted must be in the following manner.

```
(repository root)/
  .vimrc
  .vim
```

## Role Variables

name | required | default | description
--- | --- | --- | ---
vim_conf_repo | yes | |
vim_conf_cloned_dest | yes | |
vim_conf_undodir | no | | vim's undodir path. If this variable is set, this directory is created
vim_conf_version | no | HEAD |

## Dependencies

Nothing.

## Example Playbook

```yaml
- hosts: servers
  roles:
  - role: suzuki-shunsuke.vim-conf
    vim_conf_repo: "https://github.com/suzuki-shunsuke/vim.conf"
    vim_conf_cloned_dest: "{{ansible_env.HOME}}/repos/src/github.com/suzuki-shunsuke/vim.conf"
    vim_conf_undodir: "{{ansible_env.HOME}}/.vimundo"
    vim_conf_version: develop
```

## License

[MIT](LICENSE)
