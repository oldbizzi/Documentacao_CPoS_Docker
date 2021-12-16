
1. Antes de tudo, precisamos fazer a sincronização dos nós coletando o tempo por meio de um comando na shell do Linux, portanto execute e salve o resultado obtido:
```bash
$ date +%s
```
2. No arquivo node.py, na variável ```startTime``` (no final do arquivo) colar o resultado do passo anterior.

3. Por fim, próximo da linha 400, no laço:

```python  
if((1500 - (nowTime - startTime)) > 0):
  time.sleep(1500 - (nowTime - startTime))
  self.startThreads()
```
4. O valor de 1500 utilizado, representa o contado apartir do resultado do passo 2 para que o nó do CPoS inicie sua execução em **segundos**. Caso o tempo que você demore para colocar tudo para funcionar seja alto, **aumente** este tempo, se for baixo, **reduza**.

5. Com a Dockerfile pronta, executar:

```bash
$ docker build -t <nome_da_imagem> <pasta_com_dockerfile>
```

6. Agora com a imagem gerada, podemos colocar o swarm para rodar.
```
$ docker swarm init
$ docker create service --replicas 4 <nome_da_imagem> <nome_do_servico>
```
