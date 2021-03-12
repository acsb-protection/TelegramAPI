# AULA 04

**Install node ubuntu**

```text
sudo apt install curl
curl -sL https://deb.nodesource.com/setup_10.x | sudo -E bash -
sudo apt install nodejs
```

Para alterar a busca pelo Backend\(API\), basta editar `src/agent.js` e alterar `API_ROOT` para a URL do servidor local \(por exemplo, `http: //backend.cloudcamp.cf:3000/api`\)  
  
**Start da aplicação em modo DEV**

```text
sudo git clone https://github.com/treinacloud/cloudcamp-frontend
npm install
npm start
```

**CORS S3**

```text
[
    {
        "AllowedHeaders": [
            "*"
        ],
        "AllowedMethods": [
            "HEAD",
            "GET",
            "PUT",
            "POST",
            "DELETE"
        ],
        "AllowedOrigins": [
            "*"
        ],
        "ExposeHeaders": [
             "ETag",
             "x-amz-meta-custom-header"]
    }
]
```

**Dependência do Apache**

```text
a2enmod headers
```

```text
<VirtualHost *:80>
ServerName backend.cloudcamp.cf
DocumentRoot /var/www/cloudcamp-backend/public
<Directory /var/www/cloudcamp-backend>
AllowOverride All
</Directory>
ErrorLog ${APACHE_LOG_DIR}/error.log
CustomLog ${APACHE_LOG_DIR}/access.log combined
Header set Access-Control-Allow-Origin "*"
</VirtualHost>
```

**apache\_stop.sh modificado**

```text
#!/bin/bash
 
#Stop no servidor web apache2
a2enmod headers
service apache2 stop
if [ ! -d '/var/www/cloudcamp-backend' ]
then
  echo "Caminho nao existe..."
else
  rm -r '/var/www/cloudcamp-backend'
fi
```

Stress no servidor ubuntu

```text
sudo apt-get install stress

#iniciar stress na maquina
stress -c 2 &

htop


#matar processo stress
sudo pkill -f stress
```

