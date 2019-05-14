FROM postgres
MAINTAINER Marcus de Melo Moreira
RUN mkdir importacao
RUN su root 
RUN apt-get update
RUN apt-get -f install
RUN apt-get -y install wget
RUN apt-get -y install git
RUN apt-get -y install unzip
WORKDIR /importacao
RUN wget 'https://repositorio-temporario.s3-sa-east-1.amazonaws.com/Pentaho/data-integration1.zip'
RUN unzip data-integration1.zip
RUN mkdir p_modelo_gitlab
WORKDIR /p_modelo_gitlab
RUN su root
EXPOSE 5432