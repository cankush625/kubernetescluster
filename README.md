# Ansible Collection - cankush625.kubernetescluster

This collection contains the roles for configuring the Kubernetes master and slave nodes. Currently, it supports Amazon Linux 2 and Redhat Enterprise Linux v8.

kube_master
-----------

This is the role for configuring Kubernetes master node. You can find more information about it in the roles/kube_master/README.md file.

kube_slave
----------

This is the role for configuring Kubernetes slave node. You can find more information about it in the roles/kube_slave/README.md file.

Using this collection
---------------------

Download and install this collection using following command<br>

`ansible-galaxy collection install cankush625.kubernetescluster`

Example playbook for using kube_master role from this collection

    - hosts: kube_master
      collections:
        - cankush625.kubernetescluster

      roles:
        - role: kube_master
          pod_network_cidr: 10.240.0.0/16
          owner: ec2-user
          group: ec2-user

Example playbook for using kube_slave role from this collection

    - hosts: kube_slave
      collections:
        - cankush625.kubernetescluster

      roles:
        - role: kube_slave
          kube_join_command: "kubeadm join <YOUR_KUBE_MASTER_NODE_PRIVATE_IP>:6443 --token <YOUR_TOKEN>     --discovery-token-ca-cert-hash <YOUR_DISCOVERY_TOKEN_CERT_HASH> "

License
-------
MIT

Author
------
[Ankush Chavan](https://www.linkedin.com/in/ankushchavan)
