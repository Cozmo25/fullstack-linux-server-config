# Linux Server Project

# INSTRUCTIONS

## How to run the project
1. Project Github repo is: https://github.com/Cozmo25/linux-server-config
2. Open a web browser and navigate to: http://54.255.227.255/
3. Project Python & python library dependencies are:
    * Python 2.7
    * Python PIP
    * Apache 2 web server
    * PostgreSQL databsase
    * Flask Python Framework
    * mod_wsgi - Web Server Gateway Interface
    * SQL Alchemy
    * Git
    * oauth2client
    * application.py
    * database_setup.py
    * lotsofproducts.py
    * Other Python libraries: httplib2, json, requests, random, string

Note: -- aplication, database_setup & lotsofproducts.py files re hosted on the AWS server. Its necessary to install Python PIP, Flask-SQL Alchemy via the Ubuntu apt package manager. Other Python libraries can be installed via pip (see relevant documentation for how to install).

There is nothing further for the user to install.

4. Explore the Snowboard Stores and their inventory
5. If you wish to add your own store log in via Google authentication so that you can access the relevant pages on the site.


### Notes & Acknowledgments

Summary of configuration changes made to the Ubuntu server:
    * SSH port changed from 22 to 2200
    * UFW & Lightsail firewall services enabled and set to allow:
        * All outgoing connections
        * Incoming connections for: ssh, www, ntp, tcp/2200
    * 'grader' user created and given sudo access
    * ssh access set up for 'grader' user using ssh key
    * Configured timezone to UTC
    * Configured Apache to serve a Python mod_wsgi app
    * Configured PostreSQL to not allow remote connections

Users are able to navigate around the public areas of the site, but unable to alter records unless logged in.

The site uses Google authentication to login users.

Users may only amend Store / Product data that they created.

### JSON Endpoints

The following JSON endpoints are available for access to data from the app:

* All Stores Information: http://54.255.227.255/store/JSON
* Product Information for a Single Store: http://54.255.227.255/store/<Store_ID>/JSON
* Single Product of a Store Information: http://54.255.227.255/store/<Store_ID>/product/<Product_ID>/JSON


Thanks to the following sources for assistance with various elements of the project:
* [Udacity Full Stack Developer Course Notes](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004)
* [Python 2.7 Documentation](https://docs.python.org/2/index.html)
* [Udactiy Forums](https://discussions.udacity.com)
* [PostgreSQL Documentation](https://www.postgresql.org/docs/9.5/static/index.html)
* [Stackoverflow Forums](https://www.stackoverflow.com)
* [SQL Alchemy Documentation](http://docs.sqlalchemy.org/en/latest/)
* [Digital Ocean Guide: How to Deploy a Flask App on an Ubuntu VPS](https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps)
______________________________________________________________________________

## PROJECT INFO & DESCRIPTION

[Link to Project Info](https://classroom.udacity.com/nanodegrees/nd004/parts/ab002e9a-b26c-43a4-8460-dc4c4b11c379/modules/357367901175461/lessons/4340119836/concepts/48065785530923)

### How will I complete this project?

This project is linked to the Configuring Linux Web Servers course, which teaches you to secure and set up a Linux server. By the end of this project, you will have one of your web applications running live on a secure web server.

To complete this project, you'll need a Linux server instance. We recommend using Amazon Lightsail for this. If you don't already have an Amazon Web Services account, you'll need to set one up. Once you've done that, here are the steps to complete this project.

Get your server.
1. Start a new Ubuntu Linux server instance on Amazon Lightsail. There are full details on setting up your Lightsail instance on the next page.
2. Follow the instructions provided to SSH into your server.

Secure your server.
3. Update all currently installed packages.
4. Change the SSH port from 22 to 2200. Make sure to configure the Lightsail firewall to allow it.
5. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123).

Warning: When changing the SSH port, make sure that the firewall is open for port 2200 first, so that you don't lock yourself out of the server. Review this video for details! When you change the SSH port, the Lightsail instance will no longer be accessible through the web app 'Connect using SSH' button. The button assumes the default port is being used. There are instructions on the same page for connecting from your terminal to the instance. Connect using those instructions and then follow the rest of the steps.
Give grader access.
In order for your project to be reviewed, the grader needs to be able to log in to your server.

6. Create a new user account named grader.
7. Give grader the permission to sudo.
8. Create an SSH key pair for grader using the ssh-keygen tool.

Prepare to deploy your project.
9. Configure the local timezone to UTC.
10. Install and configure Apache to serve a Python mod_wsgi application.
11. Install and configure PostgreSQL:

Do not allow remote connections
Create a new database user named catalog that has limited permissions to your catalog application database.
12. Install git.

Deploy the Item Catalog project.
13. Clone and setup your Item Catalog project from the Github repository you created earlier in this Nanodegree program.
14. Set it up in your server so that it functions correctly when visiting your server’s IP address in a browser. Make sure that your .git directory is not publicly accessible via a browser!