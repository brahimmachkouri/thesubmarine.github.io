---
description: >-
  SuBox is a (BETA) pre-configured Vagrant Box with a full array of features to
  get you up and running with Vagrant in no time.
---

# SuBox

![SuBoxes](https://raw.githubusercontent.com/brahimmachkouri/subox-infos/master/images/vagrant-virtualbox-debian.png)

![SuBox](https://raw.githubusercontent.com/brahimmachkouri/subox-infos/master/images/subox3.png)

## Get Started <a id="get-started"></a>

It’s easy :

1. Download and Install [Vagrant](https://www.vagrantup.com/downloads.html)
2. Download and Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)

Then, in a terminal, just clone the repo and run vagrant up :

```text
$ git clone https://github.com/brahimmachkouri/subox my-project
$ cd my-project
$ vagrant up
```

Then visit [http://192.168.33.11](http://192.168.33.11/)

## License <a id="license"></a>

MIT License

## Features <a id="features"></a>

* Debian 9
* Apache 2.4 \(mod\_proxy\_fcgi activated\)
* SSH
* PHP 7.0 \(php7.0-fpm\), PHP errors On, MSSQL client ready, [PsySH](http://psysh.org/)
* MariaDB 10.1, Sqlite3
* Git, Go lang in the box
* laravel, symfony command line tools included
* PHPMyAdmin, PHPUnit, [composer](https://getcomposer.org/doc/01-basic-usage.md), [wp-cli](https://make.wordpress.org/cli/handbook/quick-start/), [drush](http://www.drush.org/en/master/usage/)
* Email catching with [MailHoge](https://github.com/mailhog/MailHog) : your mails are captured and displayed in a web interface
* [Ansible](https://www.ansible.com/) in the box, so you can use [Ansible Galaxy](https://galaxy.ansible.com/list#/roles?page=1&page_size=40&order=-download_count,name) to customize your box
* Virtualbox additions installed
* supervision : [monit](https://mmonit.com/monit)
* admin panels : [webmin](http://www.webmin.com/)

## Accounts <a id="accounts"></a>

| Username | Password |
| :--- | :--- |
| vagrant | vagrant |
| root | root |

## MariaDB <a id="mariadb"></a>

| PHPMyAdmin URL | http://192.168.33.11/phpmyadmin |
| :--- | :--- |
| Hostname | localhost |
| Username | root |
| Password | root |
| Database | mabase |

* Yarn, Node.js, nvm, gulp, grunt, bower, webpack, yo…

  > Even though these are packaged into the Vagrant box, we always recommend running node and any packages from your local machine and not within the box. This is strictly a performance thing. They only exist as helpers if you don’t/can’t set those up.

## Development <a id="development"></a>

* Just put your files \(PHP, HTML, JS…\) in the **public** directory \(in the box : /var/www/public, or in the **public** directory that you can see next to the Vagrantfile\) :

![Public directory](https://raw.githubusercontent.com/brahimmachkouri/subox-infos/master/images/public4.png)

* You can enter the box using ssh :

  Or :

  ```text
  ssh vagrant@192.168.33.11
  ```

## Frameworks Ready <a id="frameworks-ready"></a>

You have to connect to the box via ssh to use the following tools.

The frameworks will be installed in /var/www/

* Laravel :
* Symfony :
* Code Igniter :

## CMS Ready <a id="cms-ready"></a>

You have to connect to the box via ssh to use the following tools.  
 The CMS will be installed in /var/www/

* Wordpress via [wp-cli](https://make.wordpress.org/cli/handbook/quick-start/) :

  ```text
  cd /var/www/public
  wp core download --locale=fr_FR
  ```

* October CMS :
* Prestashop :

  But I strongly advise to disable the shared folder if you want to work with Prestashop \(as Virtualbox is known to have slow performance when shared folders are used\) by commenting the following line in Vagrantfile \(just add a \# in front of the line\) :

  ```text
  config.vm.synced_folder ".", "/var/www", :mount_options => ["dmode=777", "fmode=666"]  
  ```

  And work via sftp \(with Filezilla for example\).

## Supervision <a id="supervision"></a>

* Monit : http://192.168.33.11:2812

| Username | Password |
| :--- | :--- |
| admin | monit |

## Admin Panels <a id="admin-panels"></a>

* Webmin : https://192.168.33.11:10000

## [MailHog](https://github.com/mailhog/MailHog) <a id="mailhog"></a>

Just connect to [http://192.168.33.11:8025](http://192.168.33.11:8025/)

Inspired by Scotch Box. 

