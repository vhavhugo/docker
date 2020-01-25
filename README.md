No Windows 10. Eu o ignorei executando o daemon do Docker no modo experimental:

1. Clique com o botão direito do mouse no ícone do Docker na bandeja do sistema do Windows
2. Vá para Configurações
3. Daemon
4. Avançado
5. Colocou o "experimental": true
6. Reinicie o Docker

//baixar imagem
docker run ubuntu

//entrar no ubuntu
docker run -it ubuntu

//entrar no terminal ubuntu
docker start -a -i ubuntu

//remover containner
docker rm 888

//remover todos os cotainers que não estão roda ndo
docker container prune

//ver as imagens
docker images

//remover imagens
docker rmi 

//terminal travou sair:
ctrl + c

//roda fora do terminal usar quando trava
docker run -d nomedaimagem

// -d = roda fora do terminal     -P = gera portas aleatorias
docker -d -P nomedaimagem

// -d = roda fora do terminal     -P = gera portas aleatorias com nome escolhido
docker -d -P --name meusite nomedaimagem

//escolhendo numero da porta
docker run -d -p 12345:80 dockersamples/static-site

//Escrever author na pagina inicial
docker run -d -P -e AUTHOR="Hugo do Valle" dockersamples/static-site

//retorna apenas os ips
docker ps -q

// executa primeiro o que está em parenteses
docker stop $(docker ps -a)

- O comando Docker run e as possibilidades de execução de um container

Segue também uma breve lista dos comandos utilizados:

- docker ps - exibe todos os containers em execução no momento.
- docker ps -a - exibe todos os containers, independentemente de estarem em execução ou não.
- docker run -it NOME_DA_IMAGEM - conecta o terminal que estamos utilizando com o do container.
- docker start ID_CONTAINER - inicia o container com id em questão.
- docker stop ID_CONTAINER - interrompe o container com id em questão.
- docker start -a -i ID_CONTAINER - inicia o container com id em questão e integra os terminais, além de permitir interação entre ambos.
- docker rm ID_CONTAINER - remove o container com id em questão.
- docker container prune - remove todos os containers que estão parados.
- docker rmi NOME_DA_IMAGEM - remove a imagem passada como parâmetro.
- docker run -d -P --name NOME dockersamples/static-site - ao executar, dá um nome ao container.
- docker run -d -p 12345:80 dockersamples/static-site - define uma porta específica para ser atribuída à porta 80 do container, neste caso 12345.
- docker run -d -P -e AUTHOR="Fulano" dockersamples/static-site - define uma variável de ambiente AUTHOR com o valor Fulano no container criado.

//Criando imagem com caminho
docker run -v "/var/www/" ubuntu

//inspecionar o container
docker inspect e2f

//Montando volumes
//entrar dentro do container
docker run -it -v "C:\Users\vhavh:/var/www/" ubuntu