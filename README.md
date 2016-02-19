ansible-role-aws-security-groups
=========

This role is used to generate aws security groups inside of a specified VPC.


Requirements
------------

* AWS account
* VPC
* ansible
* boto

Role Variables
--------------

Dependencies
------------

Example Playbook
----------------


    - hosts: servers
      roles:
         - { role: ansible-role-aws-security-groups , x: 42 }

License
-------

BSD

Author Information
------------------

Adrian Herrera `aherrera@mgage.com`
