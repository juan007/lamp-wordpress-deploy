# INSTALLATION OF LAMP DEVELOPMENT ENVIRONMENT ON UBUNTU AND WORDPRESS DEPLOYMENT ON AWS LIGHTSAIL

---
## Table of Contents
1. [INSTALL APACHE](#install-apache)
2. [INSTALL WORDPRESS DEPENDENCIES](#install-wordpress-dependencies)
3. [CONFIGURE MYSQL USER AND CREATE DATABASE](#configure-mysql-user-and-create-database)
4. [DOWNLOAD WORDPRESS AND CONFIGURE VHOST](#download-wordpress-and-configure-vhost)
5. [WORDPRESS WIZARD](#wordpress-wizard)
6. [LIGHTSAIL WORDPRESS INSTANCE AND DNS ZONE](#lightsail-wordpress-instance-and-dns-zone)
7. [AWS DNS RECORD](#aws-dns-record)
8. [EXPORT IMPORT OF WORDPRESS FINISHED SITE](#export-import-of-wordpress-finished-site)
9. [SITE INFO](#site-info)
10. [BIGGEST CHALLENGES](#biggest-challenges)


---
## INSTALL APACHE
1. Update OS and install apache in Ubuntu.
- ![download](/images/1.png)
2. Set firewall rule
- ![download](/images/2.png)
3. Verify Installation
- ![download](/images/3.png)
- ![download](/images/4.png)

---
## INSTALL WORDPRESS DEPENDENCIES
1. Install all the necessary dependencies
- ![download](/images/5.png)

---
## CONFIGURE MYSQL USER AND CREATE DATABASE
1.  ![download](/images/6.png)
2.  ![download](/images/7.png)
3.  ![download](/images/8.png)
4.  ![download](/images/9.png)

---
## DOWNLOAD WORDPRESS AND CONFIGURE VHOST
1.  Download
- ![download](/images/10.png)
2.  Unzip
- ![download](/images/11.png)
3.  Configure VHOST and copy WordPress files
- ![download](/images/12.png)
- ![download](/images/13.png)
- ![download](/images/14.png)
- ![download](/images/15.png)
- ![download](/images/16.png)
- ![download](/images/17.png)
---
## WORDPRESS WIZARD
1.  Access the site and go trough the wizard
- ![download](/images/18.png)
- ![download](/images/19.png)
- ![download](/images/20.png)
---
## LIGHTSAIL WORDPRESS INSTANCE AND DNS ZONE
1.  Create a LightSail WordPress instance
2.  Once the instance is created go to networking and take note of public IP
- ![download](/images/21.png)

---
## AWS DNS RECORD
1.  Configure AWS record to point to LightSail site.
- ![download](/images/24.png)

---
## EXPORT IMPORT OF WORDPRESS FINISHED SITE
1.  To export the website from the development environment to the LightSail production environment I used the All-inOne WP Migration plugin
2.  Access the tool in the local site and export the site to a local file
- ![download](/images/25.png)
- ![download](/images/26.png)
- ![download](/images/27.png)
3.  Access the tool in the production environment (LightSail) and import from the previously generated file
- ![download](/images/28.png)
- ![download](/images/29.png)
- ![download](/images/30.png)

---
## SITE INFO
1.  URL
    -  [juanrg.nscctruro.ca/](http://juanrg.nscctruro.ca/) 
2.  Account
    -  user: matt
    -  password:  provided on project submission
3.  Highlights
    - The website was developed as a one page layout starting with the twenty twenty theme as a template.
    -  Extra CSS was added by implementing a child theme.
    - The work gallery is a personalized html block.  The customization was done by including own HTML and JavaScript in the block and adding CSS in the style.css file in the child theme.
    -  The contact form was implemented with the help of the WS Form Lite plugin.
    -  The sending mail functionality needed by the contact form was implemented with the help of the WP Mail SMTP plugin.
 
---
## BIGGEST CHALLENGES

1.  Themes and plugins where not downloading.
    -  This was a permission issue that was solved by giving ownership to the webserver user to the root, the themes, and the plugin directories.
2.  Creating a twenty twenty child theme
    -  For some reason the twenty twenty theme was not taking the parents theme styles even though the template property was set.  This was not the case for other themes where I was able to test create the child themes.  What worked for me was to generate the child theme with the help of the plugin Child Theme Configurator.
3.  Adding own HTML and JavaScript
    -  I wanted my work gallery to look exactly the same as my portfolio site done with plane HTML, CSS and JavaScript.  In order to that in the work section I implemented a HTML block where I put my own HTML and JavaScript code, the CSS was done in the style.css file in the child theme.
4.  Deleting Powered by WordPress from the footer.
    -  I wanted to delete this from the footer and could not find a way to do it from the WordPress GUI.  I had to copy the footer.php file to my child theme and modify that file to delete that part of the footer.
5.  Enabling WordPress Site to send emails, needed for contact form.
    -  The contact form is not able to send emails if the WordPress site is not configured for sending emails.  I used the WP Mail SMTP plugin to configure the email with my Gmail account.  In order to that I had to configure my Gmail account and generate a key to allow the plugin to use my account to send the emails.
