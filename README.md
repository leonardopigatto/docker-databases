# Ambiente de banco de dados para Docker

## 💻 Ambiente

### Descrição:

Ambiente com várias opções de bancos de dados e ferramentas para gerenciamento dos mesmos.

- [x] MySQL 5
- [x] phpMyAdmin
- [x] PostgreSQL
- [x] pgAdmin
- [x] MongoDB
- [x] Mongo Express
- [x] Neo4j (ONgBD 3.6.0)

### Porta(s) das aplicações:

- MySQL: `3306`.
- phpMyAdmin: `8090`.
- PostgreSQL: `5432`.
- pgAdmin: `8092`.
- MongoDB: `27017`.
- Mongo Express: `8093`.
- Neo4j: `7687` e `7474`.

## 🚀 Execução

### Pré-requisitos:

- Docker e Docker Compose.
- Não ter nenhuma aplicação executando nas portas 8090, 3306, 8091, 5432, 8092, 27017, 7474 e 7687.

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

# Encerra e remove os containers
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

#### Neo4j

- http://localhost:7474/.

- Connect URL: `bolt://localhost:7687`.
- Username: `neo4j`.
- Password: `neo4j`.

## :warning: Avisos

### Alteração de usuário, senha e banco de dados:

- Recomenda-se que altere o usuário, senha e banco de dados no arquivo `docker-compose.yml`.

### Dados persistentes:

- Os arquivos dos bancos de dados se encontram dentro da pasta `.docker`, para apagá-los é necessário ter permissões `sudo`.