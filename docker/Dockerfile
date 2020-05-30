FROM debian
ADD debian.list /etc/apt/sources.list.d/
RUN apt-get update && apt-get -y upgrade && apt -y install nginx && apt-get clean && \
    cd /var/www/ && rm -rf ./* && \
    mkdir -p ivanshulyachenko.com/img && \
    chmod -R 754 /var/www/ivanshulyachenko.com/ && \
    useradd Ivan && groupadd Shulyachenko && usermod -aG Semin Daniil && \
    chown -R Ivan:Shulyachenko /var/www/daniilsemin.com/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/ivanshulyachenko.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user Ivan/g' /etc/nginx/nginx.conf
ADD index.html /var/www/ivanshulyachenko.com/
ADD img.jpg /var/www/ivanshulyachenko.com/img/
CMD ["nginx", "-g", "daemon off;"]