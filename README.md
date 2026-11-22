# znuny

https://github.com/genilsonaborges/znuny-commands/blob/main/Znuny_install_EN.md

## Install Ubuntu 26.04
```
cd /opt
curl -L https://github.com/znuny/Znuny/archive/refs/tags/rel-7_3_8.tar.gz -o /opt/znuny-7.3.8.tar.gz
tar xfz znuny-7.3.8.tar.gz
mv /opt/Znuny-rel-7_3_8/ /opt/znuny

# mariadb
sudo apt install mariadb-client mariadb-server
vim /etc/mysql/mariadb.conf.d/50-znuny_config.cnf
[mysql]
max_allowed_packet=256M
[mysqldump]
max_allowed_packet=256M
[mysqld]
innodb_log_file_size = 256M
max_allowed_packet=256M

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

```
### Install Perl Modules
#### Check Perl modules
```
sudo apt install libpackage-stash-perl libpackage-stash-xs-perl
/opt/znuny/bin/otrs.CheckModules.pl
Apache::DBI
Apache2::Reload
Archive::Tar
Archive::Zip
Authen::SASL
Crypt::Eksblowfish::Bcrypt
Crypt::JWT
Crypt::OpenSSL::X509
CSS::Minifier::XS
Data::UUID
Date::Format
DateTime
DateTime::TimeZone
DBI
DBD::mysql
DBD::ODBC
DBD::Oracle
DBD::Pg
Digest::SHA
Encode::HanExtra
Excel::Writer::XLSX
Hash::Merge
iCal::Parser
IO::Socket::SSL
JavaScript::Minifier::XS
Jq
JSON::XS
List::Util::XS
LWP::UserAgent
Mail::IMAPClient
IO::Socket::SSL
Authen::NTLM
ModPerl::Util
Moo
Net::DNS
Net::LDAP
Net::LDAP::Constant
Net::SAML2
Net::SMTP
Spreadsheet::XLSX
Template
Template::Stash::XS
Text::Diff::FormattedHTML
Text::CSV_XS
Time::HiRes
Time::Piece
XML::LibXML
XML::LibXSLT
XML::Parser
YAML::XS
```
#### Install Perl modules
```
Установил помогло
sudo apt install libapache-dbi-perl
sudo apt install libarchive-zip-perl
sudo apt install libcrypt-eksblowfish-perl
sudo apt install libcrypt-jwt-perl
sudo apt install libcrypt-openssl-x509-perl
sudo apt install libcss-minifier-xs-perl
sudo apt install libdata-uuid-perl
sudo apt install libdatetime-perl
sudo apt install libdbd-mysql-perl
sudo apt install libencode-hanextra-perl
sudo apt install libhash-merge-perl
sudo apt install libical-parser-perl
sudo apt install libjavascript-minifier-xs-perl
sudo apt install libmail-imapclient-perl
sudo apt install libauthen-ntlm-perl
sudo apt install libmoo-perl
sudo apt install libnet-dns-perl
sudo apt install libnet-ldap-perl
sudo apt install libspreadsheet-xlsx-perl
sudo apt install libtemplate-perl
sudo apt install libtext-csv-xs-perl
sudo apt install libxml-libxml-perl
sudo apt install libxml-libxslt-perl
sudo apt install libyaml-libyaml-perl

Вариативно и не обязательно
sudo apt install libdbd-odbc-perl (MS-SQL)
sudo apt install libdbd-pg-perl (PostgreSQL)

Было установлено
sudo apt install libapache2-reload-perl
sudo apt install libarchive-tar-perl
sudo apt install libauthen-sasl-perl
sudo apt install libtimedate-perl
sudo apt install libdatetime-timezone-perl
sudo apt install libdbi-perl
sudo apt install libio-socket-ssl-perl
sudo apt install libjson-xs-perl
sudo apt install libwww-perl
sudo apt install libapache2-mod-perl2
sudo apt install libtemplate-perl
sudo apt install libtime-hires-perl
sudo apt install libtime-piece-perl
sudo apt install libxml-parser-perl

Ненашел
sudo apt install libjq-perl
sudo apt install liblist-util-perl
sudo apt install libnet-smtp-perl

Установил не помогло
sudo apt install libdigest-sha-perl
sudo apt install libexcel-writer-xlsx-perl
```

#### Last check
<img width="1412" height="771" alt="image" src="https://github.com/user-attachments/assets/a161faf1-e2e4-41db-98ef-48ac9987187b" />
