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
    <th> möglcihe Parameter</th>
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
    <td>erstmaliger Download von einem Image aus dem dann anschließend pods generiert werrden</td>
    <td></td>
  </tr>
  <tr>
    <td>kubectl run nginx</td>
    <td>nach erstmaligem Download können die Pods so gestartet werden</td>
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
  
<table>