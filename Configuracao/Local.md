# Parâmetros, configuração e execução do CPoS localmente

Para o funcionamento correto do protocolo, antes de sua execução é necessário realizar uma série de configurações utilizando um terminal bash. A configuração manual tanto quanto a configuração dos parâmetros é necessária.

## 1. Parâmetros
No arquivo parameter.py temos uma série de parâmetos configuráveis:
- `timeout` representa o tempo da rodada;
- `epsilon` define a segurança do protocolo, representando a probabilidade de reversão. Quanto menor, mais seguro.
- `TEST` tempo de teste;
- `W` número de moedas da rede;
- `q` probabilidade de nós desonestos;
- `tal` quantidade esperada de sorteios bem sucedidos dentro de uma rodada;
- `nodes` números de nós;
- `k` fração de peers, número de nós que cada nó estará conectado;
- `numStake` define a distribuição de stake nos nós. Só foi testada a distribuição igual entre os nós até agora.
## 2. Configuração
1. Antes de qualquer coisa, recomenda-se fazer uma limpeza nos processos, imagens e redes criadas:

```bash
$ sudo docker service rm cpos_cpos #remove o serviço do swarm cpos_cpos
$ sudo docker network rm netcpos #remove a rede netcpos criada
$ sudo docker image rm cpos #remove a imagem cpos criada
```

2. Feita essa remoção, precisamos coletar o tempo atual em UTC. Em um terminal:
```bash
$ python
  >python import time
  >python import datetime
  >python float(time.mktime(datetime.datetime.now()timetuple())))
```
Copie o resultado retornado por esse processo.

3. No arquivo node.py, próximo da linha 2051, atribua à variável startTime, o resultado do passo anterior:
```python
startTime = <resultado_UTC>
```

3.1 No mesmo arquivo, mas no laço que depende da variável nowTime, o valor colocado no lugar de <delay> representa o tempo decorrido (sem segundos) desde a coleta do tempo UTC no passo anterior até o início da mineração pelos nós. Portanto, se achar que irá levar mais tempo, coloque um tempo mais alto, e vice versa.
  
```python
nowTime = float(time.mktime(datetime.datetime.now().timetuple()))
print("startTime: ", startTime)        
if((<delay> - (nowTime - startTime)) > 0):
    time.sleep(<delay> - (nowTime - startTime))
self.startThreads()
```

4. No nó manager (se você estiver utilizando apenas um PC, execute neste mesmo já que será o seu manager) execute para remover o overlay network:
```bash
$ sudo docker newtork rm netcpos
```

5. Recrie a overlay network executando no manager novamente:
```bash
$ sudo docker network create --driver overlay --subnet 10.1.0.0/22 --gateway 10.1.0.1 netcpos
```
6. Devemos remover o arquivo peers.pkl, que contem a topologia da rede e recria-lo por meio dos comandos:
```bash
$ rm peers.pkl
$ python topology.py
```
## 3. Execução

Agora com toda a configuração realizada, devemos colocar o protocolo para rodar: 
  
1. Crie uma imagem do CPoS executando:
```bash
$ sudo docker build - t docker_hub/repositorio:cpos .
```
1.1 Caso você queira criar uma imagem base para subir no repositório também é possível. Isso foi feito utilizando o arquivo Dockerfile_basic, tal arquivo era renomeado como Dockerfile apenas e usado para gerar uma imagem que era submetido no repositório de imagens. Ao final deste processo os nomes eram revertidos.
  
2. Devemos subir agora o serviço no swarm executando no manager do swarm:
```bash
$ sudo docker stack deploy --compose-file docker-compose.yml cpos
```

## 4. Monitoramento
  
Para acessar a screen com o protocolo execute no terminal acessado no container nó:

  1.  `screen -d` para verificar o código do screen
  2.  `screen -r <screen code>` para  ver a screen em background

