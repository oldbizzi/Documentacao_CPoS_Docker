
# Documentação CPoS para execução no Docker Swarm e CloudLabs


Este repositório contem a documentação da execução do Comiteless Proof of Stake. O repositório contendo os códigos se encontra [aqui](https://github.com/regras/cpos_tb/tree/master), o qual contem diversos repositórios ativos cada um com uma funcionalidade específica de quando foi criado. Temos abaixo o nome do branch e uma pequena explicação sobre seu conteúdo:

<details><summary> Descrição dos Repositórios</summary>

|Branch|Descrição|Atividade|
|:------|:------:|:------:|
| [`master`](https://github.com/regras/cpos_tb/tree/master)| Futuramente vai conter a versão final do procotolo, mas atualmente está vazio.| Stale|
|[`ppos_first_version_stable`](https://github.com/regras/cpos_tb/tree/ppos_first_version_stable)|Primeira versão estável do PPoS, ainda sem a integração com o Docker sem a resolução do problema da confirmação em uma rede real de operação.|stale|
|[`ppos_second_version_stable`](https://github.com/regras/cpos_tb/tree/ppos_second_version_stable)|Segunda versão estável do PPoS, iniciada a confirmação probabilística.|stale|
|[`ppos_third_version_1`](https://github.com/regras/cpos_tb/tree/ppos_third_version_1)|Primeira versão do protocolo atual com a confirmação probabilística atual, sem Docker.|stale|
|[`ppos_third_version_2_docker_execution_gui`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_gui)|Integração da versão anterior com a interface de visualização já com a integraçã Docker|stale|
|[`ppos_third_version_2_docker_execution_transaction`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_transaction)|Versão com desenvolvimento das transações mas com foco no protocolo de consenso.|stale|
|[`ppos_third_version_2_docker_execution_unicast_transmission_header_block`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_unicast_transmission_header_block)|Versão utilizada para avaliar o desempenho em relação ao tráfego de rede produzido quando apenas os headers dos blocos são transmitidos em um primeiro momento. Logo depois, em uma segunda fase da rodada, apenas os melhores k blocos (com os menores hash de prova) são completamente transmitidos.|stale|
|[`ppos_third_version_2_docker_execution_unicast_transmission`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_unicast_transmission)|Versão com a remodelação do modelo de transmissão do bloco para que um nó enviasse apenas para seus peers. |stale|
|[`ppos_third_version_2_docker_execution`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution)|Versão com migração do Mininet para o Docker, aqui ainda sem a versão unicast.|stale|
| [`cpos_transactions`](https://github.com/regras/cpos_tb/tree/cpos_transactions) | Repositório contendo o CPoS que gera transações reais baseada no SQLite3|stale|
| [`cpos_transaction2`](https://github.com/regras/cpos_tb/tree/cpos_transaction2)| Versão melhorada do `cpos_transactions` contando com o MySQL no lugar do SQLite3 | stale|
</details>
  
  
## Execução no Swarm local
Para execução do CPoS em um ambiente Docker, mais especificamente no Swarm. Podemos utilizar tanto uma Dockerfile pura quanto um Docker Compose.
Inicialmente descreve-se o procedimento de como executar com uma Dockerfile.

- [Usando o Dockerfile](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Execu%C3%A7%C3%A3oDocker/Dockerfile.md)

- [Usando o Compose](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Execu%C3%A7%C3%A3oDocker/Docker_Compose.md)

## Documentação da execução do CPoS
Para melhor compreensão do CPoS, abaixo segue a documentação dos arquivos que compõe o CPoS, focando no branch [`ppos_third_version_2_docker_execution_unicast_transmission`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_unicast_transmission).

### <details><summary>Arquivos python</summary>

  [`block.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/block_py.md)
  
  [`blockchain.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/blockchain_py.md)
  
  [`bloom_test.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/bloom_test_py.md)
  
[`calc.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/calc_py.md)
  
[`calcProb.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/calcProb_py.md)
  
[`calc_conluio_committed.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/calc_conluio_committed_py.md)
  
  
- [`calc_m_min.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/calc_m_min_py.md)
- [`calculation.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/calculation_py.md)
- [`chaincontrol.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/chaincontrol_py.md)
- [`consensus.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/consensus_py.md)
- [`create_compose.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/create_compose_py.md)
- [`leaf.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/leaf_py.md)
- [`messages.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/messages_py.md)
- [`node.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/node_py.md)
- [`parameter.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/parameter_py.md)
- [`prob_pow.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/prob_pow_py.md)
- [`rpcclient2.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/rpcclient2_py.md)
- [`simpleNet.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/simpleNet_py.md)
- [`simpleNetbk.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/simpleNetbk_py.md)
- [`sqldb.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/sqldb_py.md)
- [`test.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/test_py.md)
- [`testConnection.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/testConnection_py.md)
- [`teste_database.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/teste_database_py.md)
- [`topology.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/topology_py.md)
- [`transaction.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/transaction_py.md)
- [`uni_test.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/uni_test_py.md)  
- [`validations.py`](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Funcionamento/utils_py.md)   

</details>
