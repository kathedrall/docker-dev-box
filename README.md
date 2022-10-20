# Docker Dev-Box

Este projeto tem como objetivo ser um ambiente de desenvolvimento completo para aplicações Web contendo até o momento:

- Servidor NGINX
- PHP 8.1
- MySQL 5.7
- REDIS
- NATS Mensageria
- VSCode server

## Setup

1. Clone o repositório
2. Crie os arquivos .env do docker e do projeto
```
cp docker/.env.example docker/.env
cp src/.env.example src/.env
```
3. Altere os valores das variáveis de ambiente conforme sua necessidade editando os arquivos .env
4. Execute o build
```
docker-compose up -d --build
```
Neste ponto você já deve ter o servidor rodando na porta 80 configurada no arquivo .env e o VSCode deve estar sendo executado na porta 8443.

**Nota:** Lembre-se de configurar uma senha forte para limitar o acesso ao VSCode.

Seu codigo estara sendo mapeado via volumes (storage) no docker. Voce ira poder acessa lo pelo terminal do vscode online, ou conectando no container App-Name-php
O Container App-Name-vscode ja esta com git instalado, facilitando o acesso a repositorios.

Voce tera uma arvore de containers, se acessar o terminal do vscode, voce estara dentro do container App-Name-vscode.
Caso necessite de ferramentas de php como o composer, via terminal, acesse o container App-Name-php. Ex.: docker exec -it App-Name-php sh
Ao acessar o container, voce estara no diretorio de trabalho podendo chamar o composer e instalar suas dependencias.


## XDebug no VSCode
Para debugar no VSCode use as seguintes configurações:
```
{
    "name": "Listen for Xdebug",
    "type": "php",
    "request": "launch",
    "port": 9000,
    "pathMappings": {
        "/src": "${workspaceFolder}/src"
    },
}
```

## Conexao Mysql, Redis e Nats
Para conectar seu cliente favorito de Mysql, Redis ou Nats, consulte o ip do seu docker e o utilize como host
```
    ipconfig em um terminal de windows
    sudo ifconfig em um terminal de linux
```
## Chave ssh 
Quando compilar o projeto, um container ira gerar uma chave ssh para voce se conectar a um repositorio git,mysql e onde mais desejar.
Para encontrar o caminho da chave 
```
    Menu File / Open File 
    Navegue ate o diretorio /config/.ssh/
    Abra o arquivo id_rsa.pub e copie a chave publica

    Ps. O Projeto ira gerar uma nova chave se voce limpar as imagens do docker.
    Ps2. Por padrao, a chave ira vir configurada com o email dev@dev. Para alterar para seu email, 
    acesse o diretorio docker/key/Dockerfile, recompile o projeto para ter a nova chave ssh.


