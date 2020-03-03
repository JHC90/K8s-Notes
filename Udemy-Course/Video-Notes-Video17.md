# [Video 17](https://www.udemy.com/course/learn-kubernetes/learn/lecture/9723312#overview)


## Pods
in eienm Pod laufen die Container(in unserem Setup die Docker). Ein Container einer Applikation läuft immer nur einmal in einem Pod, aber in einem Pod können viele unterschiedliche Applikationscontainer zeitgleich laufen. 

Ein Pod ist eine K8s Object. Das kleinste Object das mit erstellen kann. 

um load zu verteilen kommen neue pods oder neue Nodes, in einem Container wird eine Applikation niemals mehrfach deployed.

Pods haben eine 1:1 Beziehung zu einem Container einer Applikation. Aber es können mehrere unterschiedliche Container in einem Pod drin sein. 

bsp wenn eine applikation aus mehreren Diensten besteht bspw python & Mongo db. wenn man nunn ein pod erstellt kommt automatisch beides zusammen


[Link to Cloud K8S](https://kodekloud.com/p/public-labs?scenario=kubernetes-for-beginners-basiccommands-test)

[OrginalPDFzumKurs](./original.pdf)
<!--![BeispielImages](./img/1.png)-->