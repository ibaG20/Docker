# Docker

---------------------------------------------------------------------------
 ### TRABALHANDO COM CONTAINERS

 > obs: o id pode ser os 3 primeiros dígitos do id

 #### . pra rodar um container
- docker run

 #### . mostra o container q ta rodando na maquina
- docker ps 
- docker container ls

 #### . mostra tds os containers q já rodaram e tao rodando na maquina
- docker ps -a
- docker container ls -a

 #### . roda o container sem dominar o terminal
- docker run -d 

 #### . para um container 
- docker stop <id ou nome>

 #### . para expor uma porta
- docker run -d -p 80:80 (vai aparecer o container em localhost:80)

 #### . reiniciar um container
- docker start <id ou nome>

 #### . definir o nome do container
- -- name

 #### . verificando os logs
  (inevitavelmente vai aparecer um problema com o docker, e uma forma de verificar o que ta acontecendo é verificando os logs)
 - docker logs <id>

 #### . removendo containers
- docker -rm <id>
 #### . se ainda estiver rodando utiliza 
- -f

 
---------------------------------------------------------------------------
### CRIANDO IMAGENS E AVANÇANDO EM CONTAINERS

 #### . O que são imagens?
- resumidamente: intruções para rodar o container
- são originadas de arquivos que programamos para que o docker crie uma estrutura que execute determinadas ações em containers
- tem informações como: imagens base, diretório base, comandos a serem executado, porta da aplicação, etc...
- ao rodar um container baseado na imagem as intruções serão executadas em camadas

 #### . Como escolher uma boa imagem?
- podemos baixar uma imagem no site od Docker (com cuidado, pq qualquer um pode fz upload de uma imagem la)
  - imagens oficiais
  - quantidade de downloads
  - quantidade de stars

 #### . Criando uma imagem
- para criar uma imagem precisamos de um arquivo Dockerfile na pasta q vai ficar o projeto
- esse arquivo precisa de algumas intruções pra ser executado:
  - FROM   : imagem base
  - WORKDIR: diretório da aplicação
  - EXPOSE : porta da aplicação
  - COPY   : quais arquivos precisam ser copiados

 #### . Executando uma imagem
- docker build <diretorio da imagem> //é preciso fz o build
- docker run <imagem>                //e depois executar(colocar a porta nesse comando, pq a porta ta esposta só ate a camada da imagem, o container não conseguiu expor ela) 

 #### . Alterando uma imagem
- sempre q alterar o código de uma imagem vai ter q fz o build dnv
- o docker ve como uma imagem completamente nova
- depois do build vai ter q executar por outro id

 #### . Camadas das imagens
- as imagens são dividias em camadas (layers)
- cada instrução do Dockerfile representa uma layer
- quando algo é atualizado apenas as layers depois da linha atualizada são refeitas
- o resto permanece em cache

 #### . Download de imagens
- podemos fz o download de uma imagem de hub de deixa-la disponivel em nosso ambiente
- caso se use em outro container, a imagem ja estará pronta pra ser utilizada
- docker pull <imagem>



