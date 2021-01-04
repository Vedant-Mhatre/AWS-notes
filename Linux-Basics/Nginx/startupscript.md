```
sudo apt update && sudo apt upgrade -y
sudo apt install -y build-essential git
wget https://nginx.org/download/nginx-1.18.0.tar.gz && tar zxvf nginx-1.18.0.tar.gz
# PCRE version 8.42
wget https://ftp.pcre.org/pub/pcre/pcre-8.42.tar.gz && tar xzvf pcre-8.42.tar.gz

# zlib version 1.2.11
wget https://www.zlib.net/zlib-1.2.11.tar.gz && tar xzvf zlib-1.2.11.tar.gz

# OpenSSL version 1.1.0h
wget https://www.openssl.org/source/openssl-1.1.0h.tar.gz && tar xzvf openssl-1.1.0h.tar.gz

# optional NGINX dependencies:
sudo add-apt-repository -y ppa:maxmind/ppa
sudo apt update && sudo apt upgrade -y 
sudo apt install -y perl libperl-dev libgd3 libgd-dev libgeoip1 libgeoip-dev geoip-bin libxml2 libxml2-dev libxslt1.1 libxslt1-dev

rm -rf *.tar.gz

cd ~/nginx-1.18.0

./configure --prefix=/etc/nginx \ 
            --sbin-path=/usr/sbin/nginx \ 
            --modules-path=/usr/lib/nginx/modules \ 
            --conf-path=/etc/nginx/nginx.conf \
            --error-log-path=/var/log/nginx/error.log \
            --pid-path=/var/run/nginx.pid \
            --lock-path=/var/run/nginx.lock \
            --user=nginx \
            --group=nginx \
            --build=Ubuntu \
            --builddir=nginx-1.15.0 \
            --with-select_module \
            --with-poll_module \
            --with-threads \
            --with-file-aio \
            --with-http_ssl_module \
            --with-http_v2_module \
            --with-http_realip_module \
            --with-http_addition_module \
            --with-http_xslt_module=dynamic \
            --with-http_image_filter_module=dynamic \
            --with-http_geoip_module=dynamic \
            --with-http_sub_module \
            --with-http_dav_module \
            --with-http_flv_module \
            --with-http_mp4_module \
            --with-http_gunzip_module \
            --with-http_gzip_static_module \
            --with-http_auth_request_module \
            --with-http_random_index_module \
            --with-http_secure_link_module \
            --with-http_degradation_module \
            --with-http_slice_module \
            --with-http_stub_status_module \
            --with-http_perl_module=dynamic \
            --with-perl_modules_path=/usr/share/perl/5.26.1 \
            --with-perl=/usr/bin/perl \
            --http-log-path=/var/log/nginx/access.log \
            --http-client-body-temp-path=/var/cache/nginx/client_temp \
            --http-proxy-temp-path=/var/cache/nginx/proxy_temp \
            --http-fastcgi-temp-path=/var/cache/nginx/fastcgi_temp \
            --http-uwsgi-temp-path=/var/cache/nginx/uwsgi_temp \
            --http-scgi-temp-path=/var/cache/nginx/scgi_temp \
            --with-mail=dynamic \
            --with-mail_ssl_module \
            --with-stream=dynamic \
            --with-stream_ssl_module \
            --with-stream_realip_module \
            --with-stream_geoip_module=dynamic \
            --with-stream_ssl_preread_module \
            --with-compat \
            --with-pcre=../pcre-8.42 \
            --with-pcre-jit \
            --with-zlib=../zlib-1.2.11 \
            --with-openssl=../openssl-1.1.0h \
            --with-openssl-opt=no-nextprotoneg \
            --with-debug


make
sudo make install

cd ~
sudo ln -s /usr/lib/nginx/modules /etc/nginx/modules
sudo adduser --system --home /nonexistent --shell /bin/false --no-create-home --disabled-login --disabled-password --gecos "nginx user" --group nginx


```
