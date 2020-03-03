# [Video 23](https://www.udemy.com/course/learn-kubernetes/learn/lecture/9742478#overview)


## YAML
als input für pods, replica

## Bsp Input beschreibung
wichtig ist dass immer apiVersion, kind, metadata und spec inkludiert sind

---yaml
apiVersion: v1
kind: Pod
metadata:
  name: rss-site
  labels:
    app: web
    type: front-end
spec:
  containers:
    - name: front-end
      image: nginx
      ports:
        - containerPort: 80
    - name: rss-reader
      image: nickchase/rss-php-nginx:v1
      ports:
        - containerPort: 88
---
    

[Link to Cloud K8S](https://kodekloud.com/p/public-labs?scenario=kubernetes-for-beginners-basiccommands-test)

[OrginalPDFzumKurs](./original.pdf)
<!--![BeispielImages](./img/1.png)-->