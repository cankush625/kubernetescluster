kube_slave
=========

Ansible role for configuring Kubernetes slave node.

Requirements
------------

OS: Amazon Linux 2, RHEL8 <br>
CPU: 2 Cores <br>
RAM: 2GiB

Role Variables
--------------

| Variable                | Required | Default |Example Variable                         |
|-------------------------|----------|---------|-----------------------------------------|
| kube_join_command       | yes      |         | kube_join_command: "kubeadm join <YOUR_KUBE_MASTER_NODE_PRIVATE_IP>:6443 --token <YOUR_TOKEN>     --discovery-token-ca-cert-hash <YOUR_DISCOVERY_TOKEN_CERT_HASH> "         |

Dependencies
------------

No any dependency

Example Playbook
----------------

The example playbook below will show how to use this role:

    - hosts: kube_slave
      roles:
        - role: kube_slave
          kube_join_command: "kubeadm join <YOUR_KUBE_MASTER_NODE_PRIVATE_IP>:6443 --token <YOUR_TOKEN>     --discovery-token-ca-cert-hash <YOUR_DISCOVERY_TOKEN_CERT_HASH> "

License
-------

MIT

Author Information
------------------

[Ankush Chavan](https://www.linkedin.com/in/ankushchavan)
