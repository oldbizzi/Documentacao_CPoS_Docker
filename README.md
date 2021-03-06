
# Documentação CPoS para execução no Docker Swarm e CloudLabs


Este repositório contem a documentação da execução do Comiteless Proof of Stake. O repositório contendo os códigos se encontra [aqui](https://github.com/regras/cpos_tb/tree/master), o qual contem diversos *branches* ativos cada um com uma funcionalidade específica de quando foi criado. Temos abaixo o nome do branch e uma pequena explicação sobre seu conteúdo:

## Descrição dos Repositórios

- [`master`](https://github.com/regras/cpos_tb/tree/master): Futuramente vai conter a versão final do procotolo, mas atualmente está vazio.

- [`ppos_first_version_stable`](https://github.com/regras/cpos_tb/tree/ppos_first_version_stable): Primeira versão estável do PPoS, ainda sem a integração com o Docker sem a resolução do problema da confirmação em uma rede real de operação.

- [`ppos_second_version_stable`](https://github.com/regras/cpos_tb/tree/ppos_second_version_stable): Segunda versão estável do PPoS, iniciada a confirmação probabilística.

- [`ppos_third_version_1`](https://github.com/regras/cpos_tb/tree/ppos_third_version_1):Primeira versão do protocolo atual com a confirmação probabilística atual, sem Docker.

- [`ppos_third_version_2_docker_execution_gui`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_gui): Integração da versão anterior com a interface de visualização já com a integraçã Docker

- [`ppos_third_version_2_docker_execution_transaction`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_transaction): Versão com desenvolvimento das transações mas com foco no protocolo de consenso.

- [`ppos_third_version_2_docker_execution_unicast_transmission_header_block`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_unicast_transmission_header_block): Versão utilizada para avaliar o desempenho em relação ao tráfego de rede produzido quando apenas os headers dos blocos são transmitidos em um primeiro momento. Logo depois, em uma segunda fase da rodada, apenas os melhores k blocos (com os menores hash de prova) são completamente transmitidos.

- [`ppos_third_version_2_docker_execution_unicast_transmission`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution_unicast_transmission): Versão com a remodelação do modelo de transmissão do bloco para que um nó enviasse apenas para seus peers. 

- [`ppos_third_version_2_docker_execution`](https://github.com/regras/cpos_tb/tree/ppos_third_version_2_docker_execution): Versão com migração do Mininet para o Docker, aqui ainda sem a versão unicast.

- [`cpos_transactions`](https://github.com/regras/cpos_tb/tree/cpos_transactions): Repositório contendo o CPoS que gera transações reais baseada no SQLite3

- [`cpos_transaction2`](https://github.com/regras/cpos_tb/tree/cpos_transaction2): Versão melhorada do `cpos_transactions` contando com o MySQL no lugar do SQLite3 

  
## Configurações e execução
Para realizar a execução correta do protocolo, é necessário realizar a configuração de alguns parâmetros. Reforçamos que por hora estas configurações são imprescindíveis para o funcionamento do protocolo, mas no futuro, podem ser feitas modificações no código que torne este conteúdo obsoleto.

- [Local](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Configuracao/Local.md)
- [Cloud](https://github.com/oldbizzi/Documentacao_CPoS_Docker/blob/main/Configuracao/Cloud.md)



## Documentação da execução do CPoS
Para melhor compreensão do CPoS, neste [link](https://github.com/oldbizzi/Documentacao_CPoS_Docker/tree/main/Funcionamento) temos a documentação, ainda em construção, dos arquivos que compõe o protocolo.

## Disclaimer

Nós não desenvolvemos o protocolo de consenso CPoS, apenas estudamos sobre e montamos a documentação.


