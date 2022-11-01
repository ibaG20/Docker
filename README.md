# Docker

---------------------------------------------------------------------------
 TRABALHANDO COM CONTAINERS

obs: o id pode ser os 3 primeiros dígitos do id

 -> pra rodar um container
. docker run

 -> mostra o container q ta rodando na maquina
. docker ps 
. docker container ls

 -> mostra tds os containers q já rodaram e tao rodando na maquina
. docker ps -a
. docker container ls -a

 -> roda o container sem dominar o terminal
. docker run -d 

 -> para um container 
. docker stop <id ou nome>

 -> para expor uma porta
. docker run -d -p 80:80 (vai aparecer o container em localhost:80)

 -> reiniciar um container
. docker start <id ou nome>

 -> definir o nome do container
. -- name

 -> verificando os logs
  > inevitavelmente vai aparecer um problema com o docker, e uma forma de verificar o que ta acontecendo é verificando os logs
 . docker logs <id>

 -> removendo containers
. docker -rm <id>
 -> se ainda estiver rodando utiliza 
. -f


---------------------------------------------------------------------------
CRIANDO IMAGENS E AVANÇANDO EM CONTAINERS

