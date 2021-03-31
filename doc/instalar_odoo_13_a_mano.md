# Instalación de Odoo 13 paso a paso

1. Instalar Python

```
$sudo apt-get install -y python3 python3-pip
```
2. Instalar Librerías 

```
$sudo apt-get install -y libxml2-dev libxslt1-dev zlib1g-dev libsasl2-dev libldap2-dev libssl-dev python-dev python3-dev build-essential libffi-dev zlib1g-dev gcc

$sudo apt-get install -y python-pypdf2 python-dateutil python-feedparser python-ldap python-libxslt1 python-lxml python-mako python-openid python-psycopg2 python-babel python-pychart python-pydot python-pyparsing python-reportlab python-simplejson python-tz python-vatnumber python-vobject python-webdav python-werkzeug python-xlwt python-yaml python-zsi python-docutils python-psutil python-mock python-unittest2 python-jinja2 python-decorator python-requests python-passlib python-pil

$sudo pip3 install PyPDF2 Werkzeug==0.11.15 python-dateutil reportlab psycopg2-binary
```

5. Instalar Node  
```
$sudo apt-get install -y npm
    
$sudo ln -s /usr/bin/nodejs /usr/bin/node
    
$sudo npm install -g less less-plugin-clean-css

$sudo apt-get install -y node-less
```

6.  Instalar wkhtml2pdf
```
$sudo wget https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox_0.12.6-1.focal_amd64.deb
$sudo gdebi --n 'basename https://github.com/wkhtmltopdf/packaging/releases/download/0.12.6-1/wkhtmltox_0.12.6-1.focal_amd64.deb'
sudo ln -s /usr/local/bin/wkhtmltopdf /usr/bin
sudo ln -s /usr/local/bin/wkhtmltoimge /usr/bin
```

7. Usuario de Sistemas para Odoo
```
sudo adduser --system --home=/opt/odoo --group odoo
```
8. Instalar PostGre
```
sudo apt-get install postgresql
```
9. Usuario Postgre y Creación BBDD
```
sudo su – postgres

createuser --createdb --username postgres --no-createrole --no-superuser --pwprompt odoo
psql

ALTER USER odoo WITH SUPERUSER;

\q

exit
```
10. Copiamos el código Odoo desde GitHub
```
sudo su - odoo -s /bin/bash
git clone https://www.github.com/odoo/odoo --depth 1 --branch 14.0 --single-branch .
sudo pip3 install -r requirements.txt
exit
``` 
11. Ejecutamos Odoo
```
sudo -Hu odoo ./odoo-bin
```
 FIN.

