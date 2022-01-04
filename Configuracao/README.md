# Configuração e parâmetros do protocolo

Para o funcionamento correto do protocolo, antes de sua execução é necessário realizar uma série de configurações utilizando um terminal bash.

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

4. No nó manager (se você estiver utilizando apenas um PC, execute neste mesmo já que será o seu manager) execute para remover o overlay network:
```bash
$ sudo docker newtork rm netppos
```

5. Recrie a overlay network executando no manager novamente:
```bash
$ sudo docker network create --driver overlay --subnet 10.10.0.0/22 --gateway 10.1.0.1 netcpos
```

6. Crie uma imagem do CPoS executando:
```bash
$ sudo docker build - t docker_hub/repositorio:cpos .
```

7. Devemos subir agora o serviço no swarm executando no manager do swarm:
```bash
$ sudo docker stack deploy --compose-file docker-compose.yml cpos
```

8. 
