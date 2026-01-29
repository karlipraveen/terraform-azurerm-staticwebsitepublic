# Azure Static Website using Storage Account
- This module provisions Azure Storage Account for static website hosting.
- This is just for Terraform Demo's
- Version: 3.0.1 added

# To install Git, Docker, Java and Jenkins on Ubuntu 22.04
`sudo apt update`
`sudo apt install git`
`git --version`
`git config --global user.name "karlipraveen"`
`git config --global user.email "karlipraveen@gmail.com"`
`git config --list`

# To install java 21.0
`sudo apt update`
`sudo apt install fontconfig openjdk-21-jre`
`java -version`

# To install Jenkins
`sudo wget -O /etc/apt/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian/jenkins.io-2026.key`
`echo "deb [signed-by=/etc/apt/keyrings/jenkins-keyring.asc]" \
  https://pkg.jenkins.io/debian binary/ | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null`
`sudo apt update`
`sudo apt install jenkins`
`sudo systemctl enable jenkins`
`sudo systemctl start jenkins`
`sudo systemctl status jenkins`
`sudo cat /var/lib/jenkins/secrets/initialAdminPassword`

# Add Docker's official GPG key:
sudo apt update
sudo apt install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc

# Add the repository to Apt sources:
sudo tee /etc/apt/sources.list.d/docker.sources <<EOF
Types: deb
URIs: https://download.docker.com/linux/ubuntu
Suites: $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}")
Components: stable
Signed-By: /etc/apt/keyrings/docker.asc
EOF

# Install the Docker packages.
sudo apt update
sudo apt install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin -y
sudo systemctl status docker
sudo systemctl start docker
sudo docker run hello-world

# Manage Docker as a non-root user
sudo groupadd docker
sudo usermod -aG docker $USER
newgrp docker
docker run hello-world

