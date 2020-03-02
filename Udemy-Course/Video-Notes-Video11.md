# [Video 11](https://www.udemy.com/course/learn-kubernetes/learn/lecture/9723304#overview)


## Installation Minikube

Wichtig! Minikube ist lediglich eine Development lokal version um mit dem K8s mal zu interagieren. Das ist keine Produktivumgebung. 

ich habe in C:/ den folder k8s erstellt und hier sowohl downloads als auch executables liegen

[Installation kubectl](https://kubernetes.io/docs/tasks/tools/install-kubectl/#install-kubectl-on-windows)

[Installation Guidline Minikube](https://kubernetes.io/docs/tasks/tools/install-minikube/)

Sobald kubectl & minicube installiert sind & dem Pfad hinzugefügt sind öfnne eine Powershell als Admin und:

>**minikube start --vm-driver=hyperv**
später dann 
>**minikube start**

für die interaktion nehme ich immer die PS

![BeispielImages](./img/2.png)
![BeispielImages](./img/3.png)


Sobald das system ausgerollt ist folgende befehle:
das kommt von dem ersten [Tutorial](https://kubernetes.io/docs/setup/learning-environment/minikube/)

>**minikube start*** 
den ausgerollten Server starten

>**kubectl create deployment hello-minikube --image=k8s.gcr.io/echoserver:1.10**
Dienst starten 

>**kubectl expose deployment hello-minikube --type=NodePort --port=8080** 
Dienst starten
>**kubectl get pod**
Anzeige der laufenden Pods auf dem Server

>**minikube service hello-minikube --url** 
Return die URL
>**kubectl delete services hello-minikube** 
Service stoppen
>**kubectl delete deployment hello-minikube** 
Deployment löschen
>**minikube stop*** 
den aktuellen server stopen
>**minikube delete** 
den rollout wieder gänzlichlöschen


Für die weitere Bearbeitung arbeit wir mit entweder:
* Setting up Kubernetes on GCP
oder
* Setting up Kubernetes using Kubeadm tool




Alternativen für eine 


[Link to Cloud K8S](https://kodekloud.com/p/public-labs?scenario=kubernetes-for-beginners-basiccommands-test)

[OrginalPDFzumKurs](./original.pdf)
<!--![BeispielImages](./img/1.png)-->