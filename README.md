# Quickstart - Keycloak utilizando Postgres e PgAdmin com Docker

Este repositório trata-se de um quickstart para criação de containers para utilização de Keycloak, Postgres e PgAdmin.

Inicialmente é preciso esclarecer que as configurações aqui descritas e contidas nos arquivos deste repositório são para ambiente de desenvolvimento, é imprescindível a consulta da documentação do Keycloak para configurar de forma adequada o Keycloak no ambiente de produção. Veja o link abaixo:

[Running Keycloak in a container](https://www.keycloak.org/server/containers)
#### Passo a passo:

- Instalação do [Docker Desktop](https://www.docker.com/products/docker-desktop/)
- Faça o clone do repositório em uma pasta de sua preferência.

```bash
  git clone https://github.com/migueljeffersongit/keycloak-postgres-pgadmin-docker.git  
```

- Acesse a pasta keycloak-postgres-pgadmin-docker 

```bash
  cd keycloak-postgres-pgadmin-docker
```

- Crie as pastas "keycloak_data" e suas subpastas, bem como a pasta "postgres_data"

```bash
  mkdir keycloak_data
  mkdir keycloak_data/conf
  mkdir keycloak_data/realms
  mkdir keycloak_data/themes
  mkdir postgres_data
```
- Por fim execute os comando abaixo para criar e instanciar os containers

```bash
  docker compose -f keycloak-postgres.yml up -d
```

- Caso seja necessário parar e excluir os containers gerados basta utilizar o seguinte comando

```bash
  docker compose -f keycloak-postgres.yml down
```

#### No arquivo .env estão os usuários e senhas para acesso ao Keycloak e ao Banco de Dados

- Para acessar o Keycloak basta acessar http://localhost:8080 e acessar o console com o usuário e senha especificado no arquivo .env

![Página login keycloak](https://raw.githubusercontent.com/migueljeffersongit/keycloak-postgres-pgadmin-docker/main/img/keycloak-login.png)

- Essa é a visão inicial do console do keycloak

![Visão inicial keycloak](https://raw.githubusercontent.com/migueljeffersongit/keycloak-postgres-pgadmin-docker/main/img/keycloak-console.png)


- Acesse o PgAdmin em http://localhost:15432 e informe as credenciais de acesso. 
- Clique em criar novo server no PgAdmin
![Criar novo server PgAdmin](https://raw.githubusercontent.com/migueljeffersongit/keycloak-postgres-pgadmin-docker/main/img/pgadmin-add-server.png)

- Após isso preencha o nome do server, você poderá colocar o nome de sua preferência

![Criar novo server PgAdmin](https://raw.githubusercontent.com/migueljeffersongit/keycloak-postgres-pgadmin-docker/main/img/pgadmin-add-server-name.png)

- Agora informe os dados de conexão do banco de dados do Keycloak

![Dados conexão banco de dados keycloak](https://raw.githubusercontent.com/migueljeffersongit/keycloak-postgres-pgadmin-docker/main/img/pgadmin-add-server-conexao.png)

Observação: Lembrando que todos esses dados estão configurados no arquivo .env

- Por fim, após o acesso do banco de dados podemos verificar a estrutura criada pela aplicação do keycloak. 

![Banco de dados Keycloak](https://raw.githubusercontent.com/migueljeffersongit/keycloak-postgres-pgadmin-docker/main/img/pgadmin-banco-de-dados-keycloak.png)

## Autor

- [@Miguel Jefferson](https://github.com/migueljeffersongit)

