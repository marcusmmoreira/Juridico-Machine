Juridico Machine


docker build -f Dockerfile -t marcus/postgres .

docker run -d -p 5450:5432 --name Containerpostgres5450 marcus/postgres

docker run --name Containerpostgres5450 -p 5450:5432 -e POSTGRES_PASSWORD=process -d postgres


docker exec -it Containerpostgres5450 bash

apt-get update
apt-get install wget -y
apt-get install unzip



su postgres
psql
CREATE USER saopaulouser WITH PASSWORD 'process';
CREATE DATABASE processossaopaulodb;
GRANT ALL PRIVILEGES ON DATABASE processossaopaulodb to saopaulouser;
ALTER DATABASE processossaopaulodb OWNER TO saopaulouser;

\q
pg_restore -U modelo -h localhost -d processossaopaulodb processossaopaulodb.dump  -O -x

.




CREATE TABLE lista_processo
( id_processo INT PRIMARY KEY,
  numero_processo VARCHAR(100) NOT NULL,
  natureza_processo VARCHAR(100) NOT NULL,
  url_processo VARCHAR(500) NOT NULL,
  valor_processo MONEY
);

CREATE TABLE lista_advogados
( id_advogado INT PRIMARY KEY,
  nome_advogado VARCHAR(100) NOT NULL,
  status_pesquisado VARCHAR(50) NOT NULL
);

CREATE TABLE lista_partes
( id_parte INT PRIMARY KEY,
  nome_parte VARCHAR(100) NOT NULL,
  condicao_parte VARCHAR(100) NOT NULL,
  status_pesquisado VARCHAR(50) NOT NULL
);


CREATE TABLE lista_juiz
( id_juiz INT PRIMARY KEY,
  juiz_parte VARCHAR(100) NOT NULL,
  status_pesquisado VARCHAR(50) NOT NULL
);

CREATE TABLE lista_eventos
( id_evento INT PRIMARY KEY,
  evento_testo VARCHAR(1000) NOT NULL,
  evento_data VARCHAR(100) NOT NULL,
  status_pesquisado VARCHAR(50) NOT NULL
);