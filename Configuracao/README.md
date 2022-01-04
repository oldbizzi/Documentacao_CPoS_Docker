# Configuração e parâmetros do protocolo

Para o funcionamento correto do protocolo, antes de sua execução é necessário realizar uma série de configurações.

1. Antes de qualquer coisa, recomenda-se fazer uma limpeza nos processos, imagens e redes criadas:
```bash
sudo docker service rm cpos_cpos #remove o serviço do swarm cpos_cpos
sudo docker network rm netcpos #remove a rede netcpos criada
sudo docker image rm cpos #remove a imagem cpos criada
```
