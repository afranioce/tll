# Sistema de movimentações

O sistema foi desenvolvido em SPA usando o Angular 5 com material design 2, a API RestFull foi desenvolvida usando o framework symfony 4.1

Este projeto oferece o que for preciso para rodar a aplicação usando o [docker-compose (>=1.7)](https://docs.docker.com/compose/)

> As configurações usadas no docker serve apenas para deploy, para desenvolvimento requer outra configuração

## Baixar

```bash
$ git clone https://github.com/afranioce/tll.git --recurse-submodules
```

## Instalação

1. Compilando os contêineres

```bash
$ docker-compose build
```

2. Rodando os contêineres

```bash
$ docker-compose up -d
```

3. Preparando a API

```bash
$ docker-compose exec php composer install
```

> No `composer.json` tem os scripts necessário pra rodar a aplicação, como: criar o banco, rodar o migration, etc.

4. Aproveite ;)

## Usando

Apenas rode `docker-compose up -d`, então:

* Documentação da API: http://localhost:8000/api/doc
* Aplicação web: http://localhost

> Na tela de login requer qualquer dado, o controle não é feito pela API

## Contêineres em execução:

```bash
$ docker-compose ps
   Name                  Command               State                Ports              
---------------------------------------------------------------------------------------
tll_db_1      docker-entrypoint.sh mysqld      Up      3306/tcp, 0.0.0.0:3306->3307/tcp
tll_nginx_1   nginx -g daemon off;             Up      0.0.0.0:8000->80/tcp
tll_php_1     docker-php-entrypoint php- ...   Up      9000/tcp
tll_web_1     nginx -g daemon off;             Up      0.0.0.0:80->80/tcp
```
