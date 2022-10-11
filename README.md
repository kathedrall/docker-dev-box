# Docker Dev-Box

Este projeto tem como objetivo ser um ambiente de desenvolvimento completo para aplicações Web contendo até o momento:

- Servidor NGINX
- PHP 8.1
- MySQL 5.7
- REDIS
- NATS Mensageria

- VSCode server

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


