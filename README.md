# Managing Secrets with Vault and Consul

## Want to learn how to build this?

Check out the [post](https://testdriven.io/managing-secrets-with-vault-and-consul).

## Want to use this project?

1. Fork/Clone

1. Build the images and run the containers: ```$ docker-compose up -d --build```

1. You can now interact with both Vault and Consul. View the UIs at [http://localhost:8200/ui](http://localhost:8200/ui) and [http://localhost:8500/ui](http://localhost:8500/ui).

## Connect to the containers - Vault

1. In order to connect to the container, fisrt you should check if the container are running.
  `$ docker-compose ps`
2. Connect to the *vault* container:
  `$ docker-compose exec vault bash`

3. Once, you are in, check status `$ vault status`

4. Chech the vault server status: ```bash-4.4# vault operator init status```

5. Initialize the new vault server: ```bash-4.4# vault operator init```

6. Unseal the vault server: ```bash-4.4# vault operator unseal``` repeat this step 3 times using the key you received after initialize the vault server

## Info

check ip address:
```
$ for i in $(sudo docker ps --format {{.Names}}); do sudo docker inspect $i | jq ".[0].NetworkSettings.Networks" ;done
```