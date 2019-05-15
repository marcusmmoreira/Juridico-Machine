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
RUN wget 'https://sourceforge.net/projects/pentaho/files/Pentaho%208.2/client-tools/pdi-ce-8.2.0.0-342.zip/download'
RUN unzip download
RUN mkdir p_modelo_github
WORKDIR /p_modelo_github
RUN su root
EXPOSE 5432
