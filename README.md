# Ambiente de banco de dados para Docker

## 💻 Ambiente

### Descrição:

Ambiente com várias opções de bancos de dados e ferramentas para gerenciamento dos mesmos.

- [x] MySQL 5.7
- [x] phpMyAdmin
- [x] PostgreSQL
- [x] pgAdmin
- [x] MongoDB
- [x] Mongo Express
- [x] Redis
- [x] RedisInsight
- [x] Neo4j (ONgDB)

### Porta(s) das aplicações:

- MySQL: `3306`.
- phpMyAdmin: `8090`.
- PostgreSQL: `5432`.
- pgAdmin: `8091`.
- MongoDB: `27017`.
- Mongo Express: `8092`.
- Redis: `6379`.
- RedisInsight: `8093`.
- Neo4j: `7687` e `7474`.

## 🚀 Execução

### Pré-requisitos:

- Docker e Docker Compose.
- Não ter nenhuma aplicação executando nas portas 3306, 8090, 5432, 8091, 27017, 8092, 7687 e 7474.

### Instalação do Docker e Docker Compose:

- <a href="https://docs.docker.com/engine/install/" target="_blank">Instalação do Docker</a>
- <a href="https://docs.docker.com/compose/install/" target="_blank">Instalação do Docker Compose</a>

No Ubuntu:
```bash
# Para executar o Docker sem SUDO:
$ sudo usermod -aG docker $USER
```

### Como executar o ambiente:

```bash
# Clona a aplicação do GitHub
$ git clone https://github.com/leonardopigatto/docker-databases.git

# Acessa a pasta
$ cd docker-databases

# Remove o arquivo .gitkeep da pasta .docker
$ rm -f .docker/.gitkeep

# Constroi e reconstroi os containers
$ sudo docker-compose build

# Executa os containers (em background)
$ docker-compose up -d

# Encerra os containers
$ docker-compose down
```

### Como acessar as plataformas de gerenciamento dos bancos:

#### phpMyAdmin

- http://localhost:8090/.

- Acesso automático, dados definidos no arquivo `docker-compose.yml`.

#### pgAdmin

- http://localhost:8091/.

Acesso a plataforma:
- Usuário: `docker@databases.db`.
- Senha: `docker-pgadmin`.

Acesso ao servidor:
- Hostname/address: `postgres`.
- Port: `5431`.
- Maintenance database: `postgres`.
- Username: `postgres`.
- Password: `docker-databases`.

#### Mongo Express

- http://localhost:8092/.

- Usuário: `user_mongo`.
- Senha: `docker-databases`.

#### RedisInsight

- http://localhost:8093/.

- Host: `localhost`.
- Port: `6379`.
- Name: `Redis`.
- Username: `default`.
- Password: `docker-databases`.

#### Neo4j

- http://localhost:7474/.

- Connect URL: `bolt://localhost:7687`.
- Username: `ongdb`.
- Password: `ongdb`.

## :warning: Avisos

### Alteração de usuário, senha e banco de dados:

- Recomenda-se que altere o usuário, senha e banco de dados no arquivo `docker-compose.yml`.

### Dados persistentes:

- Os arquivos dos bancos de dados se encontram dentro da pasta `.docker`, para apagá-los é necessário ter permissões `sudo`.
