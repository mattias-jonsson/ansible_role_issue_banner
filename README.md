Ansible Role: issue_banner
=========

This Ansible role modifies the `/etc/issue` and `/etc/issue.net` files on the following Linux distributions.

- Enterprise Linux (RedHat, CentOS, Alma Linux OS, Rocky Linux etc.)
- Debian-based (Debian, Ubuntu etc.)


Role Variables
--------------

Available variables are listed below, along with default values where applicable (see `defaults/main.yml`):

| Variable               | Required | Default | Description                                                                 |
|------------------------|----------|---------|-----------------------------------------------------------------------------|
| `issue_banner_msg`     | No       |         | The message to be added to `/etc/issue`. If this variable is left empty, the file will revert to the operating system's default message. |
| `issue_banner_net_msg` | No       |         | The message to be added to `/etc/issue.net`. If this variable is left empty, the file will revert to the operating system's default message. |
| `issue_banner_backup`  | No       | `true`  | A boolean that determines whether a backup of the original files should be created before making changes. Set to `true` by default. |

Example Playbook
----------------

    - hosts: servers

      vars:
        issue_banner_msg: |
            WARNING : Unauthorized access to this system is forbidden and will be
            prosecuted by law. By accessing this system, you agree that your actions
            may be monitored if unauthorized usage is suspected.
        issue_banner_net_msg: |
            WARNING : Unauthorized access to this system is forbidden and will be
            prosecuted by law. By accessing this system, you agree that your actions
            may be monitored if unauthorized usage is suspected.
        issue_banner_backup: 'yes'

      roles:
         - issue_banner

License
-------

MIT

Author Information
------------------

Mattias Jonsson
