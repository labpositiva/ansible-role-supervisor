# Ansible Role Supervisor

[![GitHub tag](https://img.shields.io/github/tag/labpositiva/ansible-role-supervisor.svg?maxAge=2592000)](https://github.com/labpositiva/ansible-role-supervisor)
[![Build Status](https://travis-ci.org/labpositiva/ansible-role-supervisor.svg)](https://travis-ci.org/labpositiva/ansible-role-supervisor)
[![GitHub issues](https://img.shields.io/github/issues/labpositiva/ansible-role-supervisor.svg)](https://github.com/labpositiva/ansible-role-supervisor/issues)
[![GitHub license](https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square)](LICENSE)


Installs and configures [supervisor][link-supervisor] on a host.

## Requirements

 - Linux
   - none
 - OSX
   - [Homebrew][link-brew] must be installed.


## Role Variables

The default role variables in `defaults/main.yml` are:

    ---
    # defaults file for supervisor
    supervisor_apps:
      - program: name
        application_path: /home/user/project/src
        application_environment: {{ deployment_file_load_virtualenvwrapper }}
        execution: celery -A {{ app_name }} worker --loglevel=info

    supervisor_programs:
      - program: name
        command: 'command'
        user: "user"
        directory: "directory"
        numprocs: 1
        instalautostart: true
        autorestart: true
        startsecs: 10
        priority: 990
        disabled_program: name program to disabled


## Dependencies

none

## Example Playbook

See the [examples](./examples/) directory.

To run this playbook with default settings, create a basic playbook like this:

    - hosts: servers
      roles:
         - supervisor

To install a specific version:

    - hosts: servers
      roles:
         - { role: labpositiva.supervisor }

## Changelog

Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## Contributing

Please see [CONTRIBUTING](CONTRIBUTING.md) for details.

## Credits

Made with :heart: ️:coffee:️ and :pizza: by [labpositiva][link-company].

- [All Contributors][link-contributors]

[link-supervisor]: https://supervisord.org/
[link-brew]: http://brew.sh/

<!-- Other -->

[link-company]: https://github.com/labpositiva
[link-contributors]: AUTHORS
