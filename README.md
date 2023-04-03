# Arquivos docker para manutenção do servidor de identidade da aplicação

Comandos docker compose

Criar e iniciar os containers 
docker compose -f <nome_do_arquivo> up -d

Parar e remover containers e networks
docker compose -f <nome_do_arquivo> down

Comandos SH
bash <nome_do_arquivo>

Configurações keycloak (docker compose)
  command: 
       - start-dev
       - --import-realm quaando precisar importar o realm

volumes:
        - ./keycloak_data:/opt/keycloak/data
        - ./keycloak_data/realm.json:/opt/keycloak/data/import/realm.json

Configurações do postgres (docker compose)

Parâmetros JDBC. O parâmetro abaixo é apenas um exemplo, e não deve ser utilizado em produção sem conhecimento. É altamente recomendável que você leia a documentação do driver PostgreSQL JDBC para usá-lo.
    #JDBC_PARAMS: "ssl=true"