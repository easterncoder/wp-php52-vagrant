# WordPress Vagrant Boxes using PHP 5.2

This Vagrant configuration is based off [wp-vagrant](https://github.com/tierra/wp-vagrant).
I suggest that you check them out if you need to setup WordPress with different versions of PHP.

## Configurations Provided

***wordpress-php52***

* Debian 6.0 (squeeze)
* Apache 2.2 (suPHP, port 80 only)
* PHP 5.2.17 (painstakingly pulled from Dotdeb Lenny repos)
* PHP Extensions: curl, gd, imagick, mcrypt, mysql, xdebug
* PHPUnit 3.6.12
* MySQL 5.1.73
* Subversion 1.6.12, Git 1.7.2.5
* Node.js 0.10.29, Grunt

## Getting Started

1. Install both [VirtualBox](https://www.virtualbox.org/) and
   [Vagrant](http://www.vagrantup.com/).
2. Clone this repository to a convenient location for your development:
    * `git clone https://github.com/easterncoder/wp-php52-vagrant.git`
    * `cd wp-php52-vagrant`
3. Add the following to your hosts file:
    * `192.168.167.9  wordpress.local`
4. Start Vagrant: `vagrant up`

Apache is configured for dynamic vhosts and points to the `vhosts` directory.

A default `wordpress.local` is provisioned by default.

To add more vhosts, create a folder in the `vhosts` directory that matches
your hostname. Example, if your hostname is `mysite.dev` then just create the
`vhosts/mysite.dev` folder and Apache will take care of the rest.

You can reach the default WordPress install at:

* http://wordpress.local/

## MySQL Configuration

The MySQL root password is "wordpress", and all boxes
come with two pre-configured databases:

* `wordpress` (this is meant for a regular installation)
* `wordpress-tests` (this is meant for use with PHPUnit tests)

A single account with rights all databases for convenience:

* Username: `wordpress`
* Password: `wordpress`
