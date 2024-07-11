Для установки LEMP стека и Node.js на Debian 11:
1. Необходимо обновить версии пакетов и установить необходимые пакеты:
'''bash
sudo apt update
sudo apt install wget gnupg2 ca-certificates lsb-release apt-transport-https
'''

2. Установить Nginx:
'''bash
sudo apt install nginx
'''

3. Установить MySQL 8.0:
'''bash
wget https://dev.mysql.com/get/mysql-apt-config_0.8.15-1_all.deb
sudo dpkg -i mysql-apt-config_0.8.15-1_all.deb
sudo apt update
sudo apt install mysql-server
'''

4. Установить PHP 8.1:
'''bash
sudo wget -O /etc/apt/trusted.gpg.d/php.gpg https://packages.sury.org/php/apt.gpg
echo "deb https://packages.sury.org/php/ $(lsb_release -sc) main" | sudo tee /etc/apt/sources.list.d/php.list
sudo apt update
sudo apt install php8.1 php8.1-fpm php8.1-mysql
'''

5. Добавить нового пользователя без sudo:
'''bash
sudo adduser username
'''

6. Установить NVM (Node Version Manager) для управления версиями Node.js:
'''bash
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
'''

7. Добавить NVM в путь пользователя:
'''bash
echo 'export NVM_DIR="$HOME/.nvm"' >> ~/.bashrc
echo '[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"' >> ~/.bashrc
source ~/.bashrc
'''

8. Установить Node.js версии 16 и 20:
'''bash
nvm install 16
nvm install 20
'''
9. Установить Node.js для нового пользователя:
'''bash
sudo -i -u username bash << EOF
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash
source ~/.bashrc
nvm install 16
nvm install 20
'''
