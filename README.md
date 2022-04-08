# sre-ansible
A configuration management solution with Ansible for Production Kubernetes Clusters
Reference: https://github.com/PacktPublishing/Kubernetes-in-Production-Best-Practices/tree/master/Chapter04

Execute the steps to create a cluster: https://github.com/NickBaynham/sre-terraform/blob/main/clusters/README.md
```
virtualenv $HOME/ansible-k8s-workspace
source $HOME/ansible-k8s-workspace/bin/activate

pip install ansible openshift pyyaml requests

ansible-playbook -i \
/root/sre-ansible/inventories/clusters/ \
-e "worker_iam_role_arn=$(terraform output worker_iam_role_arn)" \
/root/sre-ansible/cluster.yaml

kubectl get namespaces
```
