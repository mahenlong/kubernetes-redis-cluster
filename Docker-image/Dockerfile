FROM centos
run yum install -y wget install make gcc libgcc gcc-c++ glibc-devel make \
    && mkdir -p /app/redis/{install,conf,data,log} \
    && cd /app/redis/install \
    && wget http://download.redis.io/releases/redis-5.0.4.tar.gz \
    && tar -xvzf redis-5.0.4.tar.gz \
    && cd /app/redis/install/redis-5.0.4 \
    && make \
    && make install PREFIX=/app/redis/ \
    && rm -rf /app/redis/install/*.gz \
    && touch /app/redis/conf/redis.conf \
    && mkdir /etc/redis \
    && cp redis.conf /etc/redis/redis.conf
    
CMD ["/app/redis/bin/redis-server","/etc/redis/redis.conf"]
#docker build -t redis5:0 /app/Docker/Redis/
