# linux mint

### install curl
-      sudo apt-get install ca-certificates curl
### get keyring
-      sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
### set permission keyring
-      sudo install -m 0755 -d /etc/apt/keyrings
-      sudo chmod a+r /etc/apt/keyrings/docker.asc
### add repo docker to sudo apt
-      echo   "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
      $(. /etc/os-release && echo jammy) stable" |   sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
-      sudo apt-get update

-      sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y

### make doker run without sudo
-      sudo usermod -aG docker $USER

-      newgrp docker
