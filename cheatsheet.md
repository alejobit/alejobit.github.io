## Cheatsheet

### Composer

[https://getcomposer.org/download](https://getcomposer.org/download){:target="_blank"}

```bash
php -r "copy('https://getcomposer.org/installer', 'composer-setup.php');"
php composer-setup.php --install-dir=/usr/local/bin --filename=composer
php -r "unlink('composer-setup.php');"
```

### Node Version Manager

[https://github.com/creationix/nvm](https://github.com/creationix/nvm#install-script){:target="_blank"}

```bash
nvm install node
```

### Symfony

[http://symfony.com/doc/current/setup.html](http://symfony.com/doc/current/setup.html#creating-symfony-applications){:target="_blank"}

```bash
# Symfony Installer
sudo mkdir -p /usr/local/bin
sudo curl -LsS http://symfony.com/installer -o /usr/local/bin/symfony
sudo chmod a+x /usr/local/bin/symfony

# Symfony 2 File Permissions
sudo setfacl -dR -m u:www-data:rwX -m u:`whoami`:rwX app/cache app/logs
sudo setfacl -R -m u:www-data:rwX -m u:`whoami`:rwX app/cache app/logs

# Symfony 3 File Permissions
sudo setfacl -dR -m u:www-data:rwX -m u:`whoami`:rwX var
sudo setfacl -R -m u:www-data:rwX -m u:`whoami`:rwX var
```

### Laravel

[https://laravel.com/docs](https://laravel.com/docs){:target="_blank"}

```bash
# Laravel Installer
composer global require laravel/installer
export PATH=$PATH:~/.config/composer/vendor/bin

# Composer Create-Project
composer create-project --prefer-dist laravel/laravel blog

# Setting up File Permissions
sudo setfacl -dR -m u:www-data:rwX -m u:`whoami`:rwX storage bootstrap/cache
sudo setfacl -R -m u:www-data:rwX -m u:`whoami`:rwX storage bootstrap/cache
```

### PPA for PHP

[https://launchpad.net/~ondrej/+archive/ubuntu/php](https://launchpad.net/~ondrej/+archive/ubuntu/php){:target="_blank"}

```bash
sudo LC_ALL=C.UTF-8 add-apt-repository ppa:ondrej/php
```

### ISO to USB

```bash
sudo fdisk -l
sudo umount /dev/sdb
sudo dd if=/path/to/iso of=/dev/sdb bs=4M
```
