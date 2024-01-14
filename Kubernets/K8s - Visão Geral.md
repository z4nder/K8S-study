https://kubernetes.io/pt-br/docs/concepts/overview/

O Kubernetes é uma *plataforma* open-source, para o gerenciamento de cargas e serviços distribuídos em containers. Possui um ecossistema grande, com amplas ferramentas disponíveis.

Seu nome Kubernetes é originado do Grego e K8s é uma abreviação da contagem das 8 letras entre k e s. Foi lançado como open-source em 2014, reunindo mais  de 15 anos de experiencia da google derivados do [[Borg o pai do K8s]].

Para começarmos e entender a utilidade  do K8s podemos voltar no tempo e entender a [[Historia dos deploys]].


### Por que você precisa do Kubernetes e o que ele pode fazer 

O containers são uma ótima escolha para empacotar e executar seus app em ambiente de produção, mas você precisa gerenciar os containers e garantir que não tenha tempo de inatividade.
Por exemplo se um container cair, outro precisa ser inicializado, o K8s se presta a justamente gerenciar esses processos.

Nesse contexto o K8s surge, oferecendo uma estrutura para executar sistemas distributors de forma resiliente. Algumas das funções dele são:
- Escalonamento
- Recuperação de falhas
- Padrões de implantação
- Balanceamento de carga
- Gerenciamento de configuração e chaves

### O que o K8s não é ?

o Kubernetes não é um sistema de orquestração, ele elimina a necessidade de orquestração. A definição técnica de orquestração é a execução de um fluxo de trabalho definido: primeiro faça A, depois B e depois C. Em contraste, o Kubernetes compreende um conjunto de processos de controle independentes e combináveis que conduzem continuamente o estado atual em direção ao estado desejado fornecido. Não importa como você vai de A para C. O controle centralizado também não é necessário. Isso resulta em um sistema que é mais fácil de usar e mais poderoso, robusto, resiliente e extensível.

### [API](https://kubernetes.io/docs/concepts/overview/kubernetes-api/)

O core do K8s é acessível por uma API HTTPs que permite aos usuários finais fazerem seus clusters e componentes externos se comunicarem entre si.

Essa API nos permite consultar e manipular os diversos objetos: Pods, namespaces, ConfigMaps e eventos.

A maior parte das acoes pode ser feita via linha de comando com o [[Instalando e usando]] que usam a API por meio de chamadas Rest.

Caso precise desenvolver algum app que se comunique diretamente com a API considere alguns desses [clients.](https://kubernetes.io/docs/reference/using-api/client-libraries/)

Vejamos o funcionamento prático do K8s aqui [[K8s - Visão Geral]]