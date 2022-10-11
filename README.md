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


