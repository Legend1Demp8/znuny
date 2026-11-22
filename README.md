# znuny

## Install Ubuntu 26.04
```
cd /opt
curl -L https://github.com/znuny/Znuny/archive/refs/tags/rel-7_3_8.tar.gz -o /opt/znuny-7.3.8.tar.gz
tar xfz znuny-7.3.8.tar.gz
mv /opt/Znuny-rel-7_3_8/ /opt/znuny

# mariadb
sudo apt install mariadb-client mariadb-server

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
### Perl Modules
# check perl modules
sudo apt install libpackage-stash-perl libpackage-stash-xs-perl
/opt/znuny/bin/otrs.CheckModules.pl

```
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
