# kubecluster-playbook

mkdir ~/kube-cluster

cd ~/kube-cluster

Create a file named ~/kube-cluster/hosts using vi or your favorite text editor:

vi ~/kube-cluster/hosts

~/kube-cluster/hosts
[masters]
master ansible_host=master_ip ansible_user=root

[workers]
worker1 ansible_host=worker_1_ip ansible_user=root
worker2 ansible_host=worker_2_ip ansible_user=root

vi ~/kube-cluster/kube-dependencies.yml


first run dependencies
ansible-playbook -i hosts ~/kube-cluster/kube-dependencies.yml

next setup master
vi ~/kube-cluster/master.yml
ansible-playbook -i hosts ~/kube-cluster/master.yml

next setup worker nodes
vi ~/kube-cluster/workers.yml

ansible-playbook -i hosts ~/kube-cluster/workers.yml


then your cluster is ready
check
kubectl get nodes
