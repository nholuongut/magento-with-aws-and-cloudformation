FROM docker.elastic.co/elasticsearch/elasticsearch:5.6.10
LABEL maintainer="Nho Luong <luongutnho@hotmail.com>"
RUN bin/elasticsearch-plugin install analysis-icu \
 && bin/elasticsearch-plugin install analysis-phonetic \
 && bin/elasticsearch-plugin remove x-pack
