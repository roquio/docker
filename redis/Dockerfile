FROM redis

ARG password

COPY redis.conf /usr/local/etc/redis/redis.conf
COPY users.acl /etc/redis/users.acl

RUN sed -i -e "s/\[password\]/${password}/g" /etc/redis/users.acl

CMD [ "redis-server", "/usr/local/etc/redis/redis.conf" ]
