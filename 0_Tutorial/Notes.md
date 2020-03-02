# Hier meine Notizen zu dem Rollout von k8s Basic 

## Preparations
Hier der [Link ](https://vitux.com/install-and-deploy-kubernetes-on-ubuntu/) zu dem Tutorial : https://

* erstelle 2 vm ubuntu server 19.04
  * Hostname1 = k8s-M1   || sudo hostnamectl set-hostname master-node
  * Hostname2 = k8s-M2  || sudo hostnamectl set-hostname slave-node
* Update like always
     >sudo apt-get update && sudo apt-get -y upgrade && sudo apt-get dist-upgrade && sudo reboot
auf beiden 
* Aufbeiden muss docker installiert werden
    > sudo apt install docker.io
* Check Docker auf beiden
    > docker --version
* enable docker
    >sudo systemctl enable docker
* get Kubernetes signing key
    >sudo apt install curl


    >curl -s https://packages.cloud.google.com/apt/doc/apt-key.gpg | sudo apt-key add

* add new repo
    >sudo apt-add-repository "deb http://apt.kubernetes.io/ kubernetes-xenial main"

* Install Kubeadm auf beiden
    >sudo apt install kubeadm

    >kubeadm version


## Installation

* Disable swap memory (if running) on both the nodes
    >sudo swapoff -a

* Give Unique hostnames to each node || sofern nicht schon beim Rollout geschehen.
    >sudo hostnamectl set-hostname slave-node
    >sudo hostnamectl set-hostname master-node

* !!!!Jetzt nur Master node!!! Initialize Kubernetes on the master node
Außerdem müssen an der stelle einige Dinge notiert werden @ Check das Tutorial 
    >sudo kubeadm init --pod-network-cidr=10.244.0.0/16

    hier kommt dann ein Befehl, welchen ich rausnotieren kann und für alle Einbindungen in dieses Cluster verwenden kann // der Befehl der hierbei herauskommt einfach 1:1 kopieren, troztz Zeilenumbruch. Für das hinzufügen eines neuen nodes noch vorne weg sudo am Node ausführen, und schon ist der im Cluster//  den Master muss ich logischerweise nicht zum Cluster hinzufügen // 

    >mkdir -p $HOME/.kube

    >sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config

    >sudo chown \$(id -u):$(id -g) $HOME/.kube/config

    >sudo kubeadm init --pod-network-cidr=10.244.0.0/16

* !!!!Jetzt nur Master node!!!
Check Anzahl der Nodes im Cluster
    >kubectl get nodes


* Deploy a Pod Network through the master node || erstellen eines Netzwerkes für k8s
  > sudo kubectl apply -f https://raw.githubusercontent.com/coreos/flannel/master/Documentation/kube-flannel.yml

  >kubectl get pods --all-namespaces

  >sudo kubectl get nodes || den Befehl nichtmit root account

hier ist im Moment nur ein Node inkludiert, da der Slave noch nicht hinzugefügt wurde

* Add the slave node to the network in order to form a cluster
    > sudo kubeadm join 192.168.100.6:6443 --token 06tl4c.oqn35jzecidg0r0m --discovery-token-ca-cert-hash sha256:c40f5fa0aba6ba311efcdb0e8cb637ae0eb8ce27b7a03d47be6d966142f2204c

    Logischerweise eben den Key, den ich oben generiert habe und nich den vom Tutorial

    >sudo kubectl get nodes || am Master

    jetzt sollten beide Nodes erscheinene

