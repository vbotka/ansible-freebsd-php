## freebsd_php

[![Build Status](https://travis-ci.org/vbotka/ansible-freebsd-php.svg?branch=master)](https://travis-ci.org/vbotka/ansible-freebsd-php)

[Ansible role.](https://galaxy.ansible.com/vbotka/freebsd_php/) FreeBSD. Install and configure PHP.

Please feel free to [share your feedback and report issues](https://github.com/vbotka/ansible-freebsd-php/issues). Contributions are welcome.


# Requirements

None.


# Roles Variables

Review defaults and examples in vars.


# Workflow

1) Change shell to /bin/sh

```
shell> ansible dbserver -e 'ansible_shell_type=csh ansible_shell_executable=/bin/csh' -a 'sudo pw usermod freebsd -s /bin/sh'
```

2) Install role

```
shell> ansible-galaxy install vbotka.freebsd_php
```

3) Fit variables

```
shell> editor vbotka.freebsd_php/vars/main.yml
```

4) Create playbook and inventory

```
shell> cat php.yml

- hosts: webserver
  roles:
    - vbotka.freebsd_php
```

```
shell> cat hosts
[webserver]
<SERVER1-IP-OR-FQDN>
<SERVER2-IP-OR-FQDN>
[webserver:vars]
ansible_connection=ssh
ansible_user=freebsd
ansible_python_interpreter=/usr/local/bin/python3.7
ansible_perl_interpreter=/usr/local/bin/perl
```

5) Install and configure PHP

```
shell> ansible-playbook php.yml
```
		

# References

- [FreebSD handbook: 6.16.3. PHP](https://www.freebsd.org/doc/en/books/porters-handbook/using-php.html)
- [FreeBSD install PHP 7.2 with FPM for Nginx](https://www.cyberciti.biz/faq/freebsd-install-php-7-2-with-fpm-for-nginx/)
- [PHP-FPM - A simple and robust FastCGI Process Manager for PHP](https://php-fpm.org/)


# License

[![license](https://img.shields.io/badge/license-BSD-red.svg)](https://www.freebsd.org/doc/en/articles/bsdl-gpl/article.html)


# Author Information

[Vladimir Botka](https://botka.link)
