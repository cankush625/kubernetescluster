kube_master
=========

Ansible role for configuring Kubernetes master node.

Requirements
------------

OS: Amazon Linux 2, RHEL8 <br>
CPU: 2 Cores <br>
RAM: 2GiB

Role Variables
--------------

| Variable                  | Required | Default |Example Variable                         |
|---------------------------|----------|---------|-----------------------------------------|
| control_plane_endpoint_ip |          |         | control_plane_endpoint_ip: 10.0.20.3    |
| pod_network_cidr          | yes      |         | pod_network_cidr: 10.240.0.0/16         |
| owner                     | yes      |         | owner: ec2-user                         |
| group                     | yes      |         | group: ec2-user                         |

Dependencies
------------

No any dependency

Example Playbook
----------------

The example playbook below will show how to use this role:

    - hosts: kube_master
      roles:
        - role: kube_master
          control_plane_endpoint_ip: 10.0.20.3
          pod_network_cidr: 10.240.0.0/16
          owner: ec2-user
          group: ec2-user

License
-------

MIT

Author Information
------------------

[Ankush Chavan](https://www.linkedin.com/in/ankushchavan)
