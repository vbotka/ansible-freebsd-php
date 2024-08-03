====================================
vbotka.freebsd_php 2.6 Release Notes
====================================

.. contents:: Topics


2.6.0
=====

Release Summary
---------------
Ansible 2.17 update

Major Changes
-------------
* Supported 13.3, 14.0, and 14.1
* Upgrade to default bsd_php_version=83
* Add tasks facts.yml. Add files/php.fact
* Add var bsd_php_pkg_install default False

Minor Changes
-------------
* Update README
* Update handlers. Listen to lowercase names.
* Update debug
* Add var bsd_php_role_version
* Add vars bsd_php_conf_www_listen_url, bsd_php_conf_www_listen_sock,
  and bsd_php_conf_www_listen_url

Bugfixes
--------

Breaking Changes / Porting Guide
--------------------------------
