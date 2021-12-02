%title: K0S
%author: xavki


# MicroK8S : Intro & Installation Manuelle


Site : https://microk8s.io/

<br>

sudo apt install snapd

sudo snap install microk8s --classic

sudo usermod -a -G microk8s $USER

sudo chown -f -R $USER ~/.kube

microk8s status --wait-ready

microk8s kubectl get nodes


microk8s enable metrics-server

microk8s kubectl top nodes
