FROM postgres
MAINTAINER Marcus de Melo Moreira
RUN mkdir importacao
RUN su root 
RUN apt-get update
RUN apt-get -f install
RUN apt-get -y install wget
RUN su -
RUN apt-get install sudo
RUN apt-get install postgresql postgresql-contrib
RUN update-rc.d postgresql enable
RUN service postgresql start
RUN su postgres
RUN find /tmp/ -name .s.PGSQL.5432
RUN /etc/init.d/postgresql restart
RUN su root
EXPOSE 5432