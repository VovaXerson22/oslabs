FROM debian
ADD debian.list /etc/apt/sources.list.d/
RUN apt-get update && apt-get -y upgrade && apt -y install nginx && apt-get clean && \
    cd /var/www/ && rm -rf ./* && \
    mkdir -p vladimirhersonskii.com/img && \
    chmod -R 754 /var/www/vladimirhersonskii.com/ && \
    useradd vladimir && groupadd hersonskii && usermod -aG vladimir hersonskii && \
    chown -R vladimir:hersonskii /var/www/hersonskii.com/ && \
    sed -i 's/\/var\/www\/html/\/var\/www\/vladimirhersonskii.com/g' /etc/nginx/sites-enabled/default && \
    sed -i 's/user www-data/user vladimir/g' /etc/nginx/nginx.conf
ADD index.html /var/www/vladimirhersonskii.com/
ADD img.jpg /var/www/vladimirhersonskii/img/
CMD ["nginx", "-g", "daemon off;"]
