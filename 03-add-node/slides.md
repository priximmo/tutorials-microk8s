%title: MicroK8S
%author: xavki


# MicroK8S : ajout d'un noeud


Site : https://microk8s.io/

<br>

sudo apt install snapd

sudo snap install microk8s --classic

sudo usermod -a -G microk8s $USER

sudo chown -f -R $USER ~/.kube

microk8s status --wait-ready

microk8s add-node

microk8s leave

