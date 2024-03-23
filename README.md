# install docker
sudo yum install -y docker
# run docker
sudo service docker start

# install python3 and pip
sudo yum install python3
sudo yum install python3-pip

# install docker-compose using pip
sudo pip3 install docker-compose

# install git
sudo yum install git -y
# clone the repo
git clone https://github.com/DIMATRABO/vault-sm.git

# unsealling vault
docker-compose up -d --build
docker-compose exec vault bash
vault operator init
vault operator unseal <key>
