Heroku buildpack: pelican
=========================

Usage
-----

Example usage:

    $ ls
    content settings.py

    $ heroku create --stack cedar --buildpack http://github.com/kylef/heroku-buildpack-pelican.git

    $ git push heroku master

Pre-compiling binaries
----------------------

    mkdir -p /app

    curl http://nginx.org/download/nginx-1.0.12.tar.gz -o nginx-1.0.12.tar.gz
    tar xvzf nginx-1.0.12.tar.gz
    cd nginx-1.0.12
    ./configure --prefix=/app/nginx --without-http_rewrite_module
    make
    make install

    cd /app
    echo '1.0.12' > nginx/VERSION
    tar -zcvf nginx.tar.gz nginx
