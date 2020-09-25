# Sobre o Projeto
Esse projeto é apenas uma base, para que seus demais projetos funcionem em rede com docker de forma mais organizada e possibilitando expandir caso trabalhe com N aplicações ou micro-serviços sem dificuldade.

## Requerimentos

- Install <a href="https://docs.docker.com/install/">Docker</a>

- Install <a href="https://docs.docker.com/compose/install/">docker-compose</a>

- PHP >= 7.1

- Postgres >= 11 ou Mysql >= 5.7


## Instalação
Para o correto funcionamento dos serviços base na rede do docker, execute o comando para clonar o projeto:
```bash
git clone git@github.com:viniciusmattosrj/projetos.git
```

Para que o git não considere alterações de permissão como modificações a serem rastreadas, execute:
```
git config core.fileMode false
```

Crie os diretórios e aplique a permissão:
```
mkdir -p ./volumes/postgres11 \ 
&& mkdir -p ./volumes/mysql57novo \
&& mkdir -p ./volumes/mysql57conf \
&& mkdir -p ./volumes/postgres/config \
&& mkdir -p ./volumes/postgres/storage \
&& chmod 777 -R ./volumes
```

Para subir os containers docker execute:
```
docker-compose up -d
```

Para conectar no container no postgres: 
```
docker exec -it postgres bash
psql -U webadm;
```

Para conectar no container do mysql:
```
docker exec -it mysql bash
mysql -u root -p;
A123456;
```

Para conectar no container do redis:
```
docker exec -it redis bash
redis-cli
```

Para conectar no container do mongo:
```
docker exec -it mongo bash
mongo;
show dbs;
```

Para o acesso no <strong>POSTGRES</strong> database administration tool, use http://localhost:5050 e use as credênciais abaixo:

  - server: 10.11.0.2
  - username: webadm
  - password: A123456


Para o acesso no <strong>MYSQL</strong> database administration tool, use http://localhost:8080 e use as credênciais abaixo:

  - server: 10.11.0.3
  - username: root
  - password: A123456


## Contribuições
Caso identifique pontos
que possam ser aprimorados envie o seu PR. ;-)


## License
[MIT](https://choosealicense.com/licenses/mit/)
