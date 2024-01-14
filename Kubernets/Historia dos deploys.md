
Vamos entender o por que o K8s é tao útil votando no tempo.

![[Pasted image 20240110084000.png]]


### Era tradicional
Os aplicações eram executadas em servidores físicos. Nao havia como limitar recursos de cada aplicações, então se um app consumisse 80% dos recursos da maquina as outras eram prejudicadas, uma solução para isso era executar cada app em uma maquina diferente o que deixa muito recurso subutilizado.

### Era virtualizada
Como solução a virtualização foi introduzida. Com esse modelo podemos executar várias VMs em uma unica CPU de um servidor.
A virtualização permite que as  aplicações sejam isoladas, com um certo nível de segurança pois as informações não pode ser acessadas livremente entre elas.

A visualização permite um melhor uso dos recursos da máquina e também escalabilidade pois um app pode ser facilmente adicionado, atualizado ou derrubado sem interferir nos outros, permitindo um certo nível de orquestração de apps mesmo que bastante limitado.

### Era dos containers
Contêineres são semelhantes às VMs, mas têm propriedades de isolamento flexibilizados pelo seu runtime para compartilhar o sistema operacional (SO) entre as aplicações. 

Os contêineres são considerados leves. Semelhante a uma VM, um contêiner tem seu próprio sistema de arquivos, compartilhamento de CPU, memória, espaço de processo e muito mais. Como eles estão separados da infraestrutura subjacente, eles são *portáveis* entre nuvens e distribuições de sistema operacional. 

Contêineres se tornaram populares porque eles fornecem benefícios extra, tais como:

1. *Criação e implantação ágil de aplicações:* Bem mais fáceis de  serem criados e executado que uma VM
2. *Desenvolvimento, integração e implantação:* Facilitá o processo de deploy, rollback e permite o uso CI/CD como temos hoje.
3. *Separação entre DEV e OPS:* Podemos já construir e usar o container que o app será executado durante o desenvolvimento do app, não precisamos aguardar o momento do deploy final.
4. *Observabilidade:* Não apenas apresenta informações e métricas de SO, mas também a integridade(HealthCheck) da aplicação e outros sinais.
5. *Consistência ambiental entre desenvolvimento, teste e produção:* funciona da mesma forma no seu PC e na nuvem.
6. *Isolamento de recursos:* desempenho previsível de aplicações.
7. *Utilização de recursos:* alta eficiência e densidade.

