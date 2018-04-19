
### Actualizando Ubuntu

sudo apt update
sudo apt upgrade

### Instalar paquetes para el trabajo

sudo apt install vlc kazam php apache2 mysql-server phpmyadmin curl git python3-pip python-pip chromium-browser ruby-full zlib1g-dev build-essential libssl-dev libreadline-dev libyaml-dev libsqlite3-dev sqlite3 libxml2-dev libxslt1-dev libcurl4-openssl-dev python-software-properties libffi-dev nodejs yarn libapache2-mod-php


cd  
git clone https://github.com/rbenv/rbenv.git ~/.rbenv  
echo 'export PATH="$HOME/.rbenv/bin:$PATH"' >> ~/.bashrc  
echo 'eval "$(rbenv init -)"' >> ~/.bashrc  
exec $SHELL  

git clone https://github.com/rbenv/ruby-build.git ~/.rbenv/plugins/ruby-build  
echo 'export PATH="$HOME/.rbenv/plugins/ruby-build/bin:$PATH"' >> ~/.bashrc  
exec $SHELL  

rbenv install 2.5.0  
rbenv global 2.5.0  
ruby -v  

gem install bundler

git config --global color.ui true  
git config --global user.name "YOUR NAME"  
git config --global user.email "YOUR@EMAIL.com"  
ssh-keygen -t rsa -b 4096 -C "YOUR@EMAIL.com"  

cat ~/.ssh/id_rsa.pub

ssh -T git@github.com

curl -sL https://deb.nodesource.com/setup_8.x | sudo -E bash -
sudo apt-get install -y nodejs

gem install rails -v 5.1.4

rbenv rehash

rails -v

## Configurar Postgres

sudo sh -c "echo 'deb http://apt.postgresql.org/pub/repos/apt/ xenial-pgdg main' > /etc/apt/sources.list.d/pgdg.list"  
wget --quiet -O - http://apt.postgresql.org/pub/repos/apt/ACCC4CF8.asc | sudo apt-key add -  
sudo apt-get update  
sudo apt-get install postgresql-common  
sudo apt-get install postgresql-9.5 libpq-dev  

sudo -u postgres createuser roy -s

If you would like to set a password for the user, you can do the following  
sudo -u postgres psql  
postgres=# \password roy  

## Primeros pasos en ruby

```
#### If you want to use SQLite (not recommended)
rails new myapp

#### If you want to use MySQL
rails new myapp -d mysql

#### If you want to use Postgres
# Note that this will expect a postgres user with the same username
# as your app, you may need to edit config/database.yml to match the
# user you created earlier
rails new myapp -d postgresql

# Move into the application directory
cd myapp

# If you setup MySQL or Postgres with a username/password, modify the
# config/database.yml file to contain the username/password that you specified

# Create the database
rake db:create

rails server
```

https://gorails.com/setup/ubuntu/16.04
