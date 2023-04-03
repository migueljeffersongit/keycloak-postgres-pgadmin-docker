# Arquivos docker para manutenção do servidor de identidade da aplicação

Comandos docker compose

Importante:
Criar pastas "keycloak_data" e "postgres_data"
A pasta "keycloak_data" será utilizada caso opte por criar um volume para o container do keycloak
E a pasta "postgres_data" será utilizada para criar o volume do container de postgres.

Criar e iniciar os containers 
docker compose -f keycloak-postgres.yml up -d

Parar e remover containers e networks
docker compose -f keycloak-postgres.yml down

Configurações keycloak
  command: 
       - start-dev
       - --import-realm (quando precisar importar o realm)

volumes:        
        - ./keycloak_data/realm.json:/opt/keycloak/data/import/realm.json (quando precisar mapear o volume e importar o json do realm)

Configurações do postgres 

Parâmetros JDBC. O parâmetro abaixo é apenas um exemplo, e não deve ser utilizado em produção sem conhecimento. É altamente recomendável que você leia a documentação do driver PostgreSQL JDBC para usá-lo.
    #JDBC_PARAMS: "ssl=true"

