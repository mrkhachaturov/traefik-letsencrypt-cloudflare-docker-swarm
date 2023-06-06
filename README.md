# Traefik with Let`s Encrypt Wildcart Certificate and Cloudflare in a Docker Swarm

Install Docker Swarm.

Create a network for Traefik, config and secrets for storing the Traefik configuration on the Docker Swarm manager node before applying the configuration.

Create a network for Traefik using the command:

`docker network create -d overlay t2_proxy`
