# AULA 03

.**env**

```text
APP_NAME=Laravel
APP_ENV=local
APP_KEY=base64:kxJi8fQ6H9yezSu7cy8Gq0lpysEK+oBi2BgVVM7uFtA=
APP_DEBUG=true
APP_LOG_LEVEL=debug
APP_URL=http://localhost

#alterar dados para sua conexao do banco
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=cloudpost
DB_USERNAME=admin
DB_PASSWORD=Tqmne

SESSION_DOMAIN=www.cloudcamp.cf
JWT_SECRET=1Pwjc29GNB4Qm9LSU5kwpTiJjRrW07MXM
BROADCAST_DRIVER=log
CACHE_DRIVER=redis
SESSION_DRIVER=redis
QUEUE_DRIVER=sync
```

**Dependências SO**

```text
#add swap para micro
sudo /bin/dd if=/dev/zero of=/var/swap.1 bs=1M count=1024
sudo /sbin/mkswap /var/swap.1
sudo chmod 600 /var/swap.1
sudo /sbin/swapon /var/swap.1
sudo echo "/var/swap.1   none   swap  sw  0  0" | sudo tee -a /etc/fstab


sudo apt-get update
sudo add-apt-repository ppa:ondrej/php -y
sudo apt-get update
sudo apt install php7.1 php7.1-xml php7.1-mbstring php7.1-mysql php7.1-json php7.1-curl php7.1-cli php7.1-common php7.1-mcrypt php7.1-gd libapache2-mod-php7.1 awscli php7.1-zip -y
sudo curl -sS https://getcomposer.org/installer | php
sudo mv composer.phar /usr/bin/composer
sudo a2enmod rewrite
sudo service apache2 restart
sudo chmod -R 777 /var/www/
sudo chown -R www-data:www-data /var/www/
```

**Dependências Backend**

```text
cd /var/www && sudo git clone  https://github.com/treinacloud/cloudcamp-backend.git
cd cloudcamp-backend
sudo composer install
sudo cp .env.example .env
sudo composer require predis/predis
sudo php artisan migrate
sudo chown -R www-data:www-data /var/www/cloudcamp-backend
sudo chmod -R 777 /var/www/cloudcamp-backend
```

**Virtual Host** 

> Entrar em  /etc/apache2/sites-available/000-default.conf e substituir pelas configurações abaixo com as configuracões do seu domínio**.**
>
> \*\*\*\*

