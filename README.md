# websiteinsidemyrobots.txt

To install this on your server you must force your webserver to execute /robots.txt as PHP. 

In apache there are two ways to make your robots.txt execute PHP

NOT RECOMMENDED: Make ALL .txt files execute PHP by adding the following line to .htaccess or server config

AddType application/x-httpd-php .txt

A safer method: use mod rewrite, something like:

RewriteEngine on

RewriteRule ^/robots.txt(.*?) something.php?uri=$1 [P,L]   
