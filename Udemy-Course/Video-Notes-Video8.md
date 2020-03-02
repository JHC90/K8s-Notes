# [Video 8](https://www.udemy.com/course/learn-kubernetes/learn/lecture/9723222#overview)


## Basic-Concepts

### Nodes // monions
phsisiche oder virtuelle maschine, auf welchem k(s deployed ist) Container laufen


### Cluster
Mehrer Nodes die zusammen arbeiten und von einem Master gemanaget werden<br>




### Master
Überwacht das Cluster ob bswp ein Node failed, Verantworlich für die Orchestration<br>
K8S macht das, managet Container in einem Clustered Environment

### Componentes
#### Api Server
frontend für k8s Cluster

####  etcd
Key value store, store all data to manage the cluster => implementing logs

#### Sheduler
Distributed work, new containers are assigned to nodes

####  Controller 
Brain zur Orchestriation, checkt ob Node up or down und bringt neue nodes up

####  Container runtime
Software die die Container zum laufen bringt, in unserem Falle Docker

####  kublet
Agent der auf jedem nod eläuft, prüft dass die Container wie erwartet laufen. das ist eine CMD die man lokal installiert haben muss


### Master & Nodes
Unterschied ist dass minion / node container runtime hat und die kubelet


maste hat die Kube-Api-Server und der worker den Kublet, etcd ist am master den controller und den scheduler


kubectl ist das CMD-Interface
kubectl run hello-minikube
kubectl cluster-info
kubectl get nodes




[OrginalPDFzumKurs](./original.pdf)
<!--![BeispielImages](./img/1.png)-->
