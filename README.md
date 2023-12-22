# Home Server Docker Compose
docker-compose.yml file for my home server.

# Installation
1. Install Docker and Docker Compose. 
2. Clone this repository or download the docker-compose.yml file.
3. Change the ports as you want in the docker-compose.yml file. The ports you should change are marked in the file.
4. Run "mkdir -p ./homarr/configs ./homarr/icons ./homarr/data ./gitea ./gitea-runner"
5. Run "docker compose up -d".
6. When setting Gitea up, you should make the ssh port 2999. Then, in the ./gitea/gitea/conf/app.ini file, change or add these lines below "[server]":  
DISABLE_SSH = false  
SSH_PORT = 2999  
SSH_LISTEN_PORT = 2999  
SSH_DOMAIN = host_ip  
START_SSH_SERVER = true  
7. In Gitea runners page, add a Gitea Runner and take the token. You should put this token in the relevant spot of the gitea runner service in the docker-compose.yml file.
8. Run "docker compose down gitea-runner && docker compose up -d"
9. You should be good to go.

# Server specs
* OS: Ubuntu 22.04 jammy (Ubuntu Server)
* CPU: Intel Pentium Dual T3200 @ 2x 2GHz
* RAM: 4 GB

# Screenshots
![homarr](/screenshots/homarr.png)
