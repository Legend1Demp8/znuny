# znuny

## Install Ubuntu 26.04
```
cd /opt
curl -L https://github.com/znuny/Znuny/archive/refs/tags/rel-7_3_8.tar.gz -o /opt/znuny-7.3.8.tar.gz
tar xfz znuny-7.3.8.tar.gz
mv /opt/Znuny-rel-7_3_8/ /opt/znuny

# apache2
sudo apt update && sudo apt install -y apache2 libapache2-mod-perl2
sudo a2dismod mpm_event
sudo a2enmod mpm_prefork

sudo a2enmod perl headers filter
sudo a2enmod perl headers filter deflate cgi ssl rewrite

# user
sudo useradd -d /opt/znuny -c 'Znuny user' -g www-data -s /bin/bash -M -N znuny

# config
cp /opt/znuny/Kernel/Config.pm.dist /opt/znuny/Kernel/Config.pm

# set permissions
/opt/znuny/bin/znuny.SetPermissions.pl

# check perl modules
sudo apt install libpackage-stash-perl libpackage-stash-xs-perl
/opt/znuny/bin/otrs.CheckModules.pl

```
