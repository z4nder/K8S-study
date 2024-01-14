Existem diversas forma de se obter o K8s.

Primeiramente instalamos o kubectl que é o binário de CLI para se comunicar com a API do K8s, então podemos instalar o minikube, para podermos criar nosso cluster de desenvolvimento.

```shell
minikube start
kubectl get nodes
```

Aqui já iniciamos nosso cluster e acabamos de ver o único node chamado minikube que é control-plane ou seja o famoso nó master que é a mente por trás dos nós workers.

Podemos verificar em qual ambiente nosso kubectl está conectado com o esse primeiro comando e alterar entre eles com o segundo, como estamos usando minikube queremos estar conectado nele
```shell
kubectl config get-contexts
kubectl config use-contexts
```

Embora o K8s orquestre e execute containers, eles devem ser agrupados em um objeto chamado [[Pod]]. Um pod é o encapsulamento do container que pode ser definido em um arquivo chamado pod.yml na raiz do seu projeto

Para listar os pods que temos rodando no nosso cluster usamos
```shell
kubectl get pods
```

No momento não devemos ter nenhum pod rodando então podemos implantar o pod que criamos com o pod.yml que aponta para uma imagem de container válida com o comando.

```shell
kubectl apply -f NOME-DO-NOSSO.yml
```

Então podemos inspecionar os detalhes desse pod com o comando
```shell
kubectl describe pod NOME-DO_NOSSO-POD
```

### Conectando-se ao app
Para podemos acessar esse pod precisamos implantar um novo Objecto chamado Service, Objetos são os resource fornecidos pelo K8s, o Pod que criamos também é um Objeto.

O [[Service]] é declarado em um .yml com `kind: Service` assim como pode é `kind: Pod` e possui suas configs especificas, o que ele faz é configurar e fornecer conectividade externa ao pod,nele definimos coisas como LoadBalancer, proxy reverso e muito mais.

Agora devemos implantar esse service com o mesmo comando
```shell
kubectl apply -f NOME-DO-NOSSO.yml
```

Também podemos listar e depois descrever todos services com
```shell
kubectl get svc
kubectl describe svc NOME-DO-SERVICO
```

Agora vamos excluir o pod
```shell
kubectl delete svc NOME
kubectl delete pod NOME
```

### Objeto [[Deployment]]

