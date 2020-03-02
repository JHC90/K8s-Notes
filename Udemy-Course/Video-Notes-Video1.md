# [Video 1](https://www.udemy.com/course/learn-kubernetes/learn/lecture/9703196#overview)


Egal ob Developer, System-Admin oder Porject-Manager. Der Kurs dient der ersten Berührung.

UltimateAim: Deploy Application to Cluste(nodes die zusammenarbeiten) um high availible / Scaling. jeder Container (da wo der jeweilige dienst läuft) wird in einen Pod geschachtelt. der pod ist die kleinste Einheit die K8s. es werden nie neue container zu einem Pod hinzugefügt, es kommen immer neue Pods auf => Specificcontainer:pod = 1:1, aber differentContainer:pod kann mehr sein. In anderen Worten bsp ein ngnx läuft nur in einem pod, im gleichen pod kann aber noch eine DB laufen usw.

![BeispielImages](./img/1.png)
