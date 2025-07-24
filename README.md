# 1. Create AWS instacne
# 2. sudo apt-get update
# 3. install webserver 
   apt install apache2 -y <br>
   systemctl status apache2 <br>
   systemctl restart apache2 <br>
    systemctl enable apache2 <br>
 # install mariadb
 apt install mariadb-server <br>
 apt install mariadb-client <br>
 systemctl start mariadb <br>
 systemctl enable mariadb <br>
 systemctl status mariadb <br>
# Set musql password
 mysql_secure_installation <br>
 systemctl restart mariadb <br>

# Install Php 
apt install php php-mysql php-gd php-cli php-common -y
# Install wget and unzip 
apt install wget unzip -y
# downloard wordpress 
 wget https://wordpress.org/latest.zip

# unzip wordpress 
unzip latest.zip

# Copy All wordpress site to webserver 
 cp -r wordpress/* /var/www/html/
# Enter location and chnag ownership 
 cd /var/www/html/ <br>
 chown www-data:www-data -R /var/www/html/ <br>
ls -l
# Remove index.html 
 rm -rf index.html
# Run this public ip on browser 

# Create Database And user 
 mysql -u root -p ;<br>
create database wordpress; <br>
CREATE USER 'wpadmin' IDENTIFIED BY 'wpadminpassword'; <br>
GRANT ALL PRIVILEGES ON wordpress.* to "wpadmin"; <br>


# The uploaded file exceeds the upload_max_filesize directive in php.ini.
sudo nano /etc/php/8.1/apache2/php.ini <br>
upload_max_filesize = 100M <br>
post_max_size = 100M <br>
sudo systemctl restart apache2 <br>







