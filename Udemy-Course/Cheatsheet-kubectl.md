# Cheatsheet - <br>k8s bzw kubectl

## Allgemein
<table style="width:100%">
  <tr>
    <th>Command</th>
    <th>Umsetzung</th>
    <th> mögliche Parameter</th>
  </tr>
  <tr>
    <td>kubectl get node</td>
    <td>Liefert die Nodes retour</td>
    <td></td>
  </tr>
  <tr>
    <td>kubectl get all</td>
    <td>LAlle Objekte von dem K8S Cluster</td>
    <td></td>
  </tr>
<table>

## Pods
Hier das <a href="./TemplatePod.yml">Template-pod</a>, ein Beispiel YML file für die Erstellung eines Pods.
 <table style="width:100%">
  <tr>
    <th>Command</th>
    <th>Umsetzung</th>
    <th> mögliche Parameter</th>
  </tr>
  <tr>
    <td>kubectl get pods</td>
    <td>liefert die laufenden Pods zurück</td>
    <td>kubectl get pods -o wide <br><br>|| mehr infos wie auf welchem node der läuft, welches image usw</td>
  </tr>
   <tr>
    <td>kubectl <mark>describe</mark> pods<br><br><br>
    kubectl describe pod <mark>newpod-j5tfn</mark>
    </td>
    <td>Detailiert infos über Pods, u.a. wo die images her sind von den laufenden Pods || <br>
    und auf welchen nodes der Spass läuft|| <br>
    welche Container in dem Pod laufen</td>
    <td><mark>der name stammt von "kubectl get pods"</mark></td>
  </tr>

  <tr>
    <td>kubectl run nginx --image nginx<br><br>
   kubectl run redis --image=redis123 --generator=run-pod/v1</td>
    <td>
    erstmaliger Download von einem Image aus dem dann anschließend pods generiert werrden</td>
    <td></td>
  </tr>
  <tr>
    <td>kubectl run nginx</td>
    <td>!!! das hier ist im grunde genommen ein Deployment!!!nach erstmaligem Download können die Pods so gestartet werden</td>
    <td></td>
  </tr>
  <tr>
    <td>kubectl edit pod nginx</td>
    <td>Öffnet ein Verwaltugnsfile von dem Pod</td>
    <td></td>
  </tr>

  <tr>
    <td>kubectl delete pod nginx</td>
    <td>so werden laufende pods beendet und gelöscht</td>
    <td></td>
  </tr>
  <tr>
    <td> kubectl create -f <mark>test.yml <mark></td>
    <td>erstellt einen Pod kommend von einem Yaml file</td>
    <td></td>
  </tr>
  <tr>
    <td> kubectl delete deployment <mark>nginx.yml <mark></td>
    <td>Löschen eines ausgerollten Pods</td>
    <td></td>
  </tr>
</table> 


## Replikas

Hier das<a href="./TemplateReplica.yml">Template-Replica</a>, ein Beispiel YML file für die Erstellung eines Replicas.

<table style="width:100%">
  <tr>
    <th>Command</th>
    <th>Umsetzung</th>
    <th> mögliche Parameter</th>
  </tr>
  <tr>
    <td> kubectl create -f <mark>replication.yml <mark></td>
    <td>erstellt einen Replika kommend von einem Yaml file</td>
    <td></td>
  </tr>
   <tr>
    <td> kubectl describe replicaset <mark></td>
    <td>Beschreibung des Replikasets</td>
    <td></td>
  </tr>

  tr>
    <td> kubectl edit replicaset new-replica-set <mark></td>
    <td>update des bestehenden Replikas </td>
    <td></td>
  </tr>
  <tr>
    <td> kubectl replace -f <mark>replication.yml <mark></td>
    <td>Wenn sich die Anzahl der Replika eines ausgerollten Replika sets ändern, muss das im Yaml geändert werden und anschließend neu eingelesen werden</td>
    <td></td>
  </tr>
  tr>
    <td> kubectl scale --replicas= 3 -f <mark>replication.yml <mark></td>
    <td>hierbei wird ebenfalls eine neue Anazahl an Replikas gewartete. </td>
    <td></td>
  </tr>
  tr>
    <td> kubectl delete replicaset myapp-replicaset <mark></td>
    <td>hierbei wird ebenfalls eine neue Anazahl an Replikas gewartete. </td>
    <td></td>
  </tr>

  kubectl edit replicaset new-replica-set
  
<table>


## Deployments

Hier das <a href="./TemplateDeployment.yml">Template-Deployment</a>, ein Beispiel YML file für die Erstellung eines Replicas.

<table style="width:100%">
  <tr>
    <th>Command</th>
    <th>Umsetzung</th>
    <th>mögliche Parameter</th>
  </tr> 
  <tr>
    <td> kubectl create -f deployment-definition.yml <mark></td>
    <td>hierbei wird ebenfalls eine neue Anazahl an Replikas gewartete. </td>
    <td>kubectl create -f deployment-definition.yml --record || hier wird die Versionierung dann mit getrackt </td>
  </tr>
  <tr>
    <td> kubectl get deployments <mark></td>
    <td>Anzeige der ausgerollten Deployments, das erstellt logischerweise replikas und das wiederum Pods </td>
    <td>Wenn ich diesen Berreich mit dem get all betrachte seh ich dass der die Replikas und dei pods erstellt hat die auch seperat abrufen kann</td>
  </tr>
  <tr>
    <td> kubectl describe deployments <mark></td>
    <td>Anzeige der weiteren Infos über das Deployment </td>
    <td></td>
  </tr>
<table>

### Rollouts (gehört iwie zu deployments)

Hier das <a href="./TemplateDeployment.yml">Template-Deployment</a>, ein Beispiel YML file für die Erstellung eines Replicas.

<table style="width:100%">
  <tr>
    <th>Command</th>
    <th>Umsetzung</th>
    <th>mögliche Parameter</th>
  </tr> 
  <tr>
    <td> kubectl rollout status deployment/<mark>NameOdPod</mark></td>
    <td>Anzeige in welcher Version (revision) wir in diesem Moment sind </td>
    <td></td>
  </tr>
  <tr>
    <td> kubectl rollout history deployment/<mark>NameOdPod</mark></td>
    <td>Anzeige in welcher Version (revision) wir in diesem Moment sind </td>
    <td></td>
  </tr>
  <tr>
    <td> kubectl apply -f deployment-definition.yml<br><br>
    kubectl set image deployment/myapp nginx=nginx:1.9.1. </td>
    <td>Szenario ist in diesem BSP dass das yml geändert wurde und jetzt auf ein anderes Image bei der erslleung der Replika / Pod verweist(neu version weil halt weiter entwickelt), dann wird hierbüber nun eine neues Deployment getriggert </td>
    <td></td>
  </tr>
  <tr>
    <td> kubectl rollout undo deployment/<mark>NameOdPod</mark></td>
    <td>Rollback falls der Rollout nicht so toll läuft wie gewünscht</td>
    <td></td>
  </tr>
<table>