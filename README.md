# Docker Dev-Box

Este projeto tem como objetivo ser um ambiente de desenvolvimento completo para aplicações Web contendo até o momento:

- Servidor NGINX
- PHP
- MySQL
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