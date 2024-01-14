
O K8s pode ser entendido como o SO da nuvem, executando seu app sem depender da cloud escolhida, Google, AWS, Raspberry...
A estrutura de um Cluster é conjunto de nós, seja em uma ou várias maquinas, e existem 2 tipos de nós

- Nós mestres ou master
- Nós de Trabalho ou workers

O nó mestre contem o plano de controle dos workers, pode ser entendido como o crebro no cluster e os workers são os nós onde são executados os Apps, podemos de n master e n workers para garantir a disponibilidade do nosso App.

![[Pasted image 20240111145928.png]]

### Node master
- Servidor API
- Scheduler
- Armazenamento etcd
- Cloud Controller
- E mais...
- 
O API server é a unica parte do cluster que vc interage diretamente, quando vc envia comandos para o cluster, eles vão para o servidor de API, quando vc recebe respostar também vem do servidor de API.

O schedule escolhe quais node workers vão executar os Apps.

O etcd é onde fica o estado do cluster e do app

O Cloud Controller permite o K8s interagir com o cloud provider, balanceando carga, gerenciando volumes...

