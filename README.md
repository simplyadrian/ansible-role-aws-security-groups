ansible-role-aws-security-groups
=========

This role is used to generate aws security groups inside of a specified VPC.


Requirements
------------

- Ansible 2.0.1 or higher.

Role Variables
--------------

| parameter             | required | default | choices | comments |
| --------------------- | -------- | ------- | -------- |-------- |
| environ | yes | dev | | probably best passed as an extra var |
| state | yes | present | | |
| sg_settings | yes | {} | | |

Example Playbook
----------------

    - name: test stack creation
      hosts: test
      vars:
        sg_settings:
          testSG:
            aws_acct_vpc_id: "vpc-fa3aca9e"
            aws_region: "us-west-2"
            rules:
              - proto: tcp
                from_port: 0
                to_port: 65535
                cidr_ip: 0.0.0.0/0
              - proto: udp
                from_port: 0
                to_port: 65535
                cidr_ip: 0.0.0.0/0
              - proto: icmp
                from_port: 8
                to_port: -1
                cidr_ip: 0.0.0.0/0
            rules_egress:
              - proto: all
                cidr_ip: 0.0.0.0/0
      roles:
        - ansible-role-aws-security-groups
License
-------

BSD

Author Information
------------------

Adrian Herrera `aherrera@mgage.com`
