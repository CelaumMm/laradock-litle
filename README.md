# Laradock Litle

### Passo a passo
Clone Repositório
```sh
git clone https://github.com/CelaumMm/laradock-litle.git docker
```

Remover o .git
```sh
rm -rf docker/.git
```

Copie o diretório docker para o seu projeto
```sh
cp -r docker app-laravel/
cd app-laravel/docker
```

Crie o Arquivo .env no diretório docker
```sh
cp .env.example .env
```

Atualize as variáveis de ambiente do arquivo .env
```dosini
COMPOSE_PROJECT_NAME=laradock
PHP_VERSION=8.2
MYSQL_DATABASE=default
MYSQL_USER=default
MYSQL_PASSWORD=secret
MYSQL_PORT=3306
MYSQL_ROOT_PASSWORD=root
```

Suba os containers do projeto
```sh
# Desenvolvimento
docker-compose up -d

# Produção
docker-compose up -d nginx mysql redis php-worker
```

Acessar o container
```sh
# Acessar como usuário 
docker-compose exec --user=laradock workspace zsh
docker-compose exec --user=laradock workspace bash

# Acessar como root
docker-compose exec workspace zsh
docker-compose exec workspace bash
```
