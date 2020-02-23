## **Install and Configure Apache Web Server**
Apache is an open source web server that’s available for Linux servers free of charge

---
**To install Apache and its required dependencies**

    $ sudo apt update
    $ sudo apt install apache2

    # Verify the Apache installation
    $ apache2 -version

**Allow Apache on UFW**

    $ sudo ufw allow 'Apache'

    # Check status
    $ sudo ufw status

**Verify that the Apache service is running**
    
    $ sudo systemctl status apache2

    # Checkl if Apache listens on your IP address
    $ hostname -I

Type your IP address *192.168.X.X* in web browser If you see the page, it means that Apache has been successfully installed on your server

---
**Creating Your Own Website**

By default, Apache comes with a basic site, but We can modify its content in **/var/www/html** or **settings by editing its Virtual Host file found in /etc/apache2/sites-enabled/000-default.conf**

- Let’s start by creating a folder for our new website in /var/www/

        $ sudo mkdir /var/www/mysite/

    */mysitye/ can beany name will work, as long as we point to it in the virtual hosts configuration file later*

- Lets have an HTML file in that directory just created
        
        $ cd /var/www/mysite/
        $ nano index.html

- Past the following code in
    ```html
    <html>
    <head>
        <title> Ubuntu rocks! </title>
    </head>
    <body>
        <p> I'm running this website on an Ubuntu Server server!
    </body>
    </html>
    ```
**Setting up the VirtualHost Configuration File**
- Going into the configuration files directory

        $ cd /etc/apache2/sites-available/

- Since Apache came with a default VirtualHost file, let’s use that as a base. Now edit the configuration file:

        $ sudo nano gci.conf
- We should have our email in ServerAdmin so users can reach you in case Apache experiences any error. We also want the DocumentRoot directive to point to the directory our site files are hosted on
    - ServerAdmin yourname@example.com
    - DocumentRoot /var/www/mysite/
- The default file doesn’t come with a ServerName directive so we’ll have to add and define it by adding this line below the last directive
    - ServerName sampledomain.com

**Activating VirtualHost file**

- After setting up our website, we need to activate the virtual hosts configuration file to enable it

        $ sudo a2ensite gci.conf

- You should see the following output

        Enabling site gci.
        To activate the new configuration, you need to run:
        service apache2 reload
        
- To load the new site, we restart Apache by typing

        service apache2 reload

**Check the result by refresh your website in your browser. Hooray!!!**