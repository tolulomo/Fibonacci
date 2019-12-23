FROM nginx

# Normally we should write COPY ./default.conf /etc/nginx/conf
# But we write COPY ./default.conf /etc/nginx/conf.d/default.conf
# to ensure if a default.conf file exist, it is overwritten
COPY ./default.conf /etc/nginx/conf.d/default.conf