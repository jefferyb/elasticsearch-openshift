# https://github.com/elastic/elasticsearch-docker
FROM docker.elastic.co/elasticsearch/elasticsearch-oss:6.6.0

USER elasticsearch

COPY config/sgconfig/ config/sgconfig/
COPY bin/ bin/

# Search Guard plugin
# https://github.com/floragunncom/search-guard/wiki
RUN elasticsearch-plugin install --batch com.floragunn:search-guard-6:6.6.0-24.1 \
	&& chmod +x plugins/search-guard-6/tools/*.sh

# Generate certs for search-guard
# RUN bin/generated-certificates.sh

# Add your elasticsearch plugins setup here
# Example: RUN elasticsearch-plugin install analysis-icu

USER root
