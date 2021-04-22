# Ansible Collection - cankush625.multicloudkubernetescluster

This collection contains the roles for configuring the Multi-Cloud Kubernetes master and slave nodes. Currently, it supports Amazon Linux 2, Redhat Enterprise Linux and Ubuntu.

Roles
=====

kube_master
-----------

This is the role for configuring Kubernetes master node. You can find more information about it in the roles/kube_master/README.md file.

kube_slave
----------

This is the role for configuring Kubernetes slave node. You can find more information about it in the roles/kube_slave/README.md file.

Installation and Usage
======================

Download and install this collection using following command<br>

`ansible-galaxy collection install cankush625.multicloudkubernetescluster`

Example playbook for using kube_master role from this collection

    - hosts: kube_master
      collections:
        - cankush625.multicloudkubernetescluster

      roles:
        - role: kube_master
          control_plane_endpoint_ip: 10.0.2.3
          pod_network_cidr: 10.240.0.0/16
          owner: ec2-user
          group: ec2-user

Example playbook for using kube_slave role from this collection

    - hosts: kube_slave
      collections:
        - cankush625.multicloudkubernetescluster

      roles:
        - role: kube_slave
          kube_join_command: "kubeadm join <YOUR_KUBE_MASTER_NODE_PUBLIC_IP>:6443 --token <YOUR_TOKEN>     --discovery-token-ca-cert-hash <YOUR_DISCOVERY_TOKEN_CERT_HASH> "

Tested on
=========

This role is tested on following OS distributions: <br>
- Amazon Linux 2
- RedHat Enterprise Linux v8
- Ubuntu Server 20.04 LTS

Contribution
============

If you find any bug or want to do improvement in this collection, then find the source code for this collection [here](https://github.com/cankush625/multicloudkubernetescluster). Create an issue or open up a pull request and I will consider merging it, if it does what this collection is intended for.

License
=======

MIT

Author
======

[Ankush Chavan](https://www.linkedin.com/in/ankushchavan)
