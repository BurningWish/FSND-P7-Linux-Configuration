# Linux Server Configuration

This is the project 7 for the Full Stack Web Developer Nanodegree Program. I configure an Amazon Lightsail instance, and delopy the Catalog application on it.

## How to access the delopyed web app?

- Web app is delopyed in the public IP address ```http://174.129.191.197```. Please use Google Chrome incognito mode to browse this web app, and manually refresh the login page, if you cannot see the facebook login button.

## How to access my Lightsail Linux instance?

- My Linux instance's public IP Address is ```174.129.191.197```.
- SSH port for connecting this instance is 2200.
- ```grader``` is the username for you to login to instance.
- Password is disabled for SSH login, and you must use the privite key, which is the ```grader_key``` in this repository.
- In summary, the command for login to my instance is
```ssh grader@174.129.191.197 -i {path to the grader_key} -p 2200```

### How did I configure my Lightsail Linux instance?

- Create new user ```grader```.
- Give ```grader``` sudo access.
- Disable SSH root login.
- Disable SSH password login, and enforce private key login.
- Change the SSH port from 22 to 2200.
- Configure the uncomplicated firewall (ufw) so that only communications for HTTP(port 80), SSH(port 2200), and NTP(port 123) are allowed. In my Lightsail account page, I also configure the external firewall accordingly.
- Install ```Apache2``` webserver and ```mod_wsgi```.
- Install ```pip``` and therefore all other python libraries for my original Catalog App.
- Install ```Psycopg2``` because now we use ```Postgres``` instead of ```Sqlite``` as the database server.
- Re-structure my original Catalog App and configure the ```/etc/apache2/sites-available/catalogs.conf``` and ```/var/www/catalogs/catalogs.wsgi``` file for the app to correctly run on ```Apache2```.
