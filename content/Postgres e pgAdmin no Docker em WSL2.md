1. Rode dois containers para o postgres e pgAdmin.:
```bash
docker run --name nome_do_container --network=bridge -p 5432:5432 -e POSTGRES_PASSWORD=senha_do_postgres -d postgres:versao

docker run --name nome_do_container --network=bridge -p 5050:80 -e PGADMIN_DEFAULT_EMAIL=email_para_acessar -e PGADMIN_DEFAULT_PASSWORD=senha_para_acessar -d dpage/pgadmin4
```

2. Acesse o pgAdmin no navegador pelo `localhost:5050`.

3. Obtenha o IP do container que está rodando o postgres com `docker inspect ID_DO_CONTAINER | grep IPAddress`.

4. Conecte com o database pelo pgAdmin utilizando o IP obtido no passo anterior. Lembre-se de utilizar a porta definida na hora da criação do container do postgres.