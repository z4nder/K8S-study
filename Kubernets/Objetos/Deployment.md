O objeto de deployment tem o papel de fornecer auto recuperação, permitindo escalonamento a update contínuo.

Esse objeto é o que fornece uma das características tão desejadas do K8s. Vejamos o exemplo

```yml
apiVersion: apps/v1
kind: Deployment
metadata:
  name: best-crud-api-deployment
  labels:
	project: best-crud-api-deploy
spec:
  replicas: 5
  selector:
    matchLabels:
      project: best-crud-api
  template:
    metadata:
      labels:
        app: best-crud-api
    spec:
      containers:
      - name: web
	    imagePullPolicy: Always
        image: gusttavo212/best-crud-api:latest
        ports:
        - containerPort: 3030

```

Aqui definimos que queremos 5 replicas do indicado em matchLabels, que contem as specs da imagem no campo spec, caso um pod tenha problemas e caia de 5 -> 4 o K8s vai perceber isso e subir um novo pod, nos deixando com 5 como foi definido.

Aplicamos esse objeto usando
```shell
kubectl apply -f deploy.yml
```

Listamos dessa forma
```shell
kubectl get deployments
```