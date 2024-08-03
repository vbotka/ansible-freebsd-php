# freebsd_php

[![quality](https://img.shields.io/ansible/quality/27910)](https://galaxy.ansible.com/vbotka/freebsd_php)
[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-php.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-php)
[![GitHub tag](https://img.shields.io/github/v/tag/vbotka/ansible-freebsd-php)](https://github.com/vbotka/ansible-freebsd-php/tags)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_php/) FreeBSD. Install and configure PHP.

Feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-freebsd-php/issues).

[Contributions are welcome](https://github.com/firstcontributions/first-contributions).


## Requirements

### Collections

* community.general


## Roles Variables

Review defaults and examples in vars.


## Workflow

1) Change shell to /bin/sh if necessary

```sh
shell> ansible dbserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install the role

```yaml
shell> ansible-galaxy role install vbotka.freebsd_php
```

Install the collection if necessary

```yaml
shell> ansible-galaxy collection install community.general
```

3) Fit variables to your needs.

4) Create playbook and inventory

```yaml
shell> cat php.yml
- hosts: webserver
  roles:
    - vbotka.freebsd_php
```

```ini
shell> cat hosts
[webserver]
<SERVER1-IP-OR-FQDN>
<SERVER2-IP-OR-FQDN>
[webserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_python_interpreter=/usr/local/bin/python3.9
ansible_perl_interpreter=/usr/local/bin/perl
```

5) Install and configure PHP

Use tags to run the play step by step for the first time.

Check syntax

```sh
shell> ansible-playbook php.yml --syntax-check
```

Create custom facts

```sh
shell> ansible-playbook php.yml -t bsd_php_facts
```

Display variables

```sh
shell> ansible-playbook php.yml -t bsd_php_debug -e bsd_php_debug=true
```

Install packages or ports

```sh
shell> ansible-playbook php.yml -t bsd_php_pkg -e bsd_php_pkg_install=true
```

Configure PHP

```sh
shell> ansible-playbook php.yml -t bsd_php_conf
```

Configure rc.conf

```sh
shell> ansible-playbook php.yml -t bsd_php_rcconf
```

Run the whole playbook. The role is idempotent.

```sh
shell> ansible-playbook php.yml
```


## Ansible lint

Use the configuration file *.ansible-lint.local* when running
*ansible-lint*. Some rules might be disabled and some warnings might
be ignored. See the notes in the configuration file.

```sh
shell> ansible-lint -c .ansible-lint.local
```
		

## References

- [Apache24 and PHP 8.1 - FreeBSD Forum](https://forums.freebsd.org/threads/apache24-and-php-8-1.88994/)
- [PHP-FPM - A simple and robust FastCGI Process Manager for PHP](https://php-fpm.org/)


## License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


## Author Information

[Vladimir Botka](https://botka.info)
