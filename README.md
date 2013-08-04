dev-env
=======

A LAMP development environment built with [Vagrant](http://www.vagrantup.com/) and [Puppet](http://puppetlabs.com/) from a vanilla Ubuntu 12.04 LTS box.

## Quick Start

1. Install the required software for your **host** machine
 * Download and install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
 * Download and install [Vagrant](http://downloads.vagrantup.com/)
 * Download and install [Git](http://git-scm.com/downloads)

2. Create the parent directory for your projects
```
mkdir ~/vagrant
cd ~/vagrant
```

3. Grab the dev-env code
```
git clone https://github.com/matthewsplant/dev-env.git project_dir
cd project_dir
```

4. **Spin up your new DevOps environment**
```
    vagrant up
```

## Additional Options

1. (Optional) Automate application database creation
 * Set install, database name, user, and password in in puppet/manifest/basee.php file
 
2. (Optional) Clone your application project
 * "git-clone" your project into "www"

3. (Optional) Add *dev.localhost* to your hosts /etc/hosts file
```
    127.0.0.1       dev.localhost
```
4. (Optional) Install Phing along with additional support libraries on your new DevOps environment
```
vagrant ssh
cd /vagrant
composer install
```

## FAQ
#### Credentials
 * Ubuntu Vagrant user - **vagrant/vagrant** (not needed when you 'vagrant ssh' in)
 * MySQL Root user - **root/r00t** (set in puppet/manifest/basee.php file)
 * MySQL application database and credentials (set in puppet/manifest/base.php file)

#### Development Envrionment
 * Root URL - http://127.0.0.1:8080/ (or http://dev.localhost:8080/ if you modified your /etc/hosts file)
 * Root Directory - /vagrant/www/
 * Leverage Composer and Phing scripts for enhanced DevOps automation.

#### Virtual Machine Specifications
 * Ubuntu 12.04 LTS aka "precise32"
 * Apache 2.2.22
 * MySQL 5.5.31
 * PHP 5.3.10
 * Composer
 * Phing 2.5.0 
See http://127.0.0.1:8080/phpinfo.php for more details.

## Security Note
This virtual machine is optimized for ease of use.  It is not secured properly for production use.
