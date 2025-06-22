# System Update
sudo apt update
sudo apt upgrade -y

# Git Instalation
sudo apt install git nginx -y

# HTTPS
sudo apt update
sudo apt install \
apt-transport-https \
ca-certificates \
curl \
software-properties-common -y

# Docker GPG
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /usr/share/keyrings/docker-archive-keyring.gpg

# Adding Docker Repo to APT Sources
echo "deb [arch=$(dpkg --print-architecture) signed-by=/usr/share/keyrings/docker-archive-keyring.gpg] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null

# Updating APT packages
sudo apt update

# Installing Docker engine and Docker plugins
sudo apt install docker-ce docker-ce-cli containerd.io docker-compose-plugin -y

# Clone the repo
git clone https://github.com/mzkwcim/monitoring

# Move to the main directory of the project
mv <your-path>

# Initialize Docker Compose
docker compose up -d
