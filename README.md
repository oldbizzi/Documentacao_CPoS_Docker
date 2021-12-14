# Documenta-o-Execu-o-CPoS
Documentação sobre como executar o CPoS no Docker

Para execução do CPoS em um ambiente Docker, mais especificamente no Swarm. Podemos utilizar tanto uma Dockerfile pura quanto um Docker Compose.
Inicialmente descreve-se o procedimento de como executar com uma Dockerfile.

1. Com a Dockerfile pronta, executar:

´´´
docker build -t <nome_da_imagem> <pasta_com_dockerfile>
´´´
