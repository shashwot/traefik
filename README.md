# TRAEFIK

# Terminology

- Providers: discover the service that live on your infrastructure (Eg: ip, health, etc)
- Entrypoint: listen for incoming traffic (ports,....)
- Routers: analyse the requests (host, path, headers, SSL)
- Services: forwards the request to your service (load balancing)
- Middlewares: may update the request or make decisions based on the request (authentication, rate limiting, headers, ...)


# Available Router Configurations
traefik.http.routers.<router_name>.rule
- "traefik.http.routers.myrouter.rule=Host(`example.com`)"

traefik.http.routers.<router_name>.entrypoints
- "traefik.http.routers.myrouter.entrypoints=ep1,ep2"

traefik.http.routers.<router_name>.service
- "traefik.http.routers.myrouter.service=myservice"

traefik.http.routers.<router_name>.tls
- "traefik.http.routers.myrouter.tls=true"


# Available Service Configuration
traefik.http.services.<service_name>.loadbalancer.server.port
- "traefik.http.services.myservice.loadbalancer.server.port=8080"

traefik.http.services.<service_name>.loadbalancer.passhostheader
- "traefik.http.services.myservice.loadbalancer.passhostheader=true"

traefik.http.services.<service_name>.loadbalancer.healthcheck.path
- "traefik.http.services.myservice.loadbalancer.healthcheck.path=/foo"

traefik.http.services.<service_name>.loadbalancer.healthcheck.port
- "traefik.http.services.myservice.loadbalancer.healthcheck.port=42"
