# _Проект по стажировке от WS_
## Инструкции по развертыванию на Linux:
### Подготовка:
##### Если у вас уже установлен Docker и Docker Compose - пропустите этот шаг

###### Установка Docker
- sudo apt update
- sudo apt install apt-transport-https ca-certificates curl software-properties-common
- curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -
- sudo add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable"
- sudo apt update
- sudo apt install docker-ce -y
- sudo systemctl start docker

###### Установка Docker Compose
- sudo curl -L "https://github.com/docker/compose/releases/download/1.26.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
- sudo chmod +x /usr/local/bin/docker-compose

### Развертывание:
- В файле app/config/app_config.php прописать свои secretKey и serverName
- По желанию можно прописать свои данные для БД в файле docker-compose.yml:
  - POSTGRES_USER
  - POSTGRES_DB
  - POSTGRES_PASSWORD
- Также, вы можете изменить порт для доступа к сайту:
  - ports:
  - "<ваш порт>:80"
- В директории проекта выполнить команду docker-compose up -d
- Сайт будет доступен по адресу localhost:<ваш порт>

### [OpenApi спецификация](openapi.yaml)
