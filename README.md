docker-compose up -d --build
docker-compose exec vault bash
vault operator init
vault operator unseal <key>