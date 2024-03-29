# install docker
sudo yum install -y docker
# run docker
sudo service docker start
# add ec2 user to docker group 
sudo usermod -a -G docker ec2-user

sudo chmod 666 /var/run/docker.sock

//# install python3 and pip
//sudo yum install python3
//sudo yum install python3-pip

# docker-compose install
sudo curl -L https://github.com/docker/compose/releases/download/1.22.0/docker-compose-$(uname -s)-$(uname -m) -o /usr/local/bin/docker-compose

sudo chmod +x /usr/local/bin/docker-compose


# install git
sudo yum install git -y
# clone the repo
git clone https://github.com/DIMATRABO/vault-sm.git

# unsealling vault
docker-compose up -d --build
docker-compose exec vault bash
vault operator init
vault operator unseal <key>
