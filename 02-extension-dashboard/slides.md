%title: MicroK8S
%author: xavki


# MicroK8S : kubectl & Dashboard


Site : https://microk8s.io/

<br>

mkdir -p $HOME/.kube/config
microk8s kubectl config view --raw > $HOME/.kube/config
microk8s kubectl config view --raw > /vagrant/config

<br>


microk8s enable dashboard

TOKEN=$(microk8s kubectl -n kube-system get secret | awk '$1 ~ "default-token" {print $1}')

microk8s kubectl -n kube-system get secret $TOKEN -o jsonpath='{.data.token}' | base64 -d

microk8s kubectl port-forward -n kube-system service/kubernetes-dashboard 10443:443 --address='0.0.0.0'
