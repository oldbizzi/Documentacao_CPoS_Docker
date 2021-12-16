
# Documentação CPoS para execução no Docker Swarm e CloudLabs


Este repositório contem a documentação da execução do Comiteless Proof of Stake. O repositório contendo os códigos se encontra [aqui](https://github.com/regras/cpos_tb/tree/master), o qual contem diversos repositórios ativos cada um com uma funcionalidade específica de quando foi criado. Temos abaixo o nome do repositório e uma pequena explicação sobre seu conteúdo:


- [*cpos_transatcions*](https://github.com/regras/cpos_tb/tree/cpos_transactions): Repositório contendo o CPoS que gera transações reais baseada no SQLite3.
- [*cpos_transaction2*](https://github.com/regras/cpos_tb/tree/cpos_transaction2): Repositório idêntico ao *cpos_transactions*, porém, irá conter a implementação com MySQL.
- [*ppos_third_version_2_docker_execution_unicast_transmission*](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_unicast_transmission): Versão que o autor, Diego, utilizou para seus testes da tese.

## Execução no Swarm local
Para execução do CPoS em um ambiente Docker, mais especificamente no Swarm. Podemos utilizar tanto uma Dockerfile pura quanto um Docker Compose.
Inicialmente descreve-se o procedimento de como executar com uma Dockerfile.

- [Usando o Dockerfile](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Execu%C3%A7%C3%A3oDocker/Dockerfile.md)

- [Usando o Compose](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Execu%C3%A7%C3%A3oDocker/Docker_Compose.md)
