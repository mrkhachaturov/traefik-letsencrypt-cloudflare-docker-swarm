# Traefik with Let`s Encrypt Wildcart Certificate and Cloudflare in a Docker Swarm

Install Docker Swarm by following this [guide](https://www.heyvaldemar.com/install-docker-swarm-on-ubuntu-server/).

Create a network for Traefik, config and secrets for storing the Traefik configuration on the Docker Swarm manager node before applying the configuration.

Create a network for Traefik using the command:

`docker network create -d overlay t2_proxy`

Create a secret for storing the certificate using the command:

`docker secret create wildcard-heyvaldemar-net.crt /path/to/wildcard-heyvaldemar-net.crt`

Create a secret for storing the key using the command:

`docker secret create wildcard-heyvaldemar-net.key /path/to/wildcard-heyvaldemar-net.key`

Create a config for storing the Traefik configuration using the command:

`docker config create traefik-dynamic-configuration.yml /path/to/traefik-dynamic-configuration.yml`

Example of `traefik-dynamic-configuration.yml`:


Deploy Traefik in a Docker Swarm using the command:

`docker stack deploy -c traefik-ssl-certificate-docker-swarm.yml traefik`
