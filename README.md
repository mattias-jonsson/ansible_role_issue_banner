Ansible Role: ansible_role_motd
=========

Modifies /etc/issue and /etc/issue.net on the following Linux distributions:

<ul>
<li>CentOS 7
<li>Debian 11
<li>Ubuntu 20.04
</ul>


Requirements
---------------

None.

Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):

| Variable | Required | Default | Comments |
| -------- | -------- | ------- | -------- |
| `ansible_role_motd_issue_msg` | No | | Text to be added to /etc/issue, if variable is empty the file reverts to OS default. |
| `ansible_role_motd_issue_net_msg` | No | | Text to be added to /etc/issue.net, if variable is empty the file reverts to OS default. |
| `ansible_role_motd_backup` | No | true | Boolean, should a backup be created? |


Dependencies
------------

None.


Example Playbook
----------------


    - hosts: servers

      vars:
        ansible_role_motd_issue_msg: |
            WARNING : Unauthorized access to this system is forbidden and will be
            prosecuted by law. By accessing this system, you agree that your actions
            may be monitored if unauthorized usage is suspected.
        ansible_role_motd_issue_net_msg: |
            WARNING : Unauthorized access to this system is forbidden and will be
            prosecuted by law. By accessing this system, you agree that your actions
            may be monitored if unauthorized usage is suspected.
        ansible_role_motd_backup: 'yes'

      roles:
         - ansible_role_motd

License
-------

MIT

Author Information
------------------

Mattias Jonsson
