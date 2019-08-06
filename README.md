To set up a nginx-proxy using docker do the following:
1. docker network create nginx-proxy
2. from Powershell run $Env:COMPOSE_CONVERT_WINDOWS_PATHS=1
3. docker-compose up -d

Then in your proyects use doccker compose and make sure of the following:
environment:
            - VIRTUAL_HOST=test.domain
            - VIRTUAL_PORT=5000 (port where the web service is exposed)
        
and

networks:
  default:
    external:
      name: nginx-proxy

Use the following to stop the service:

docker-compose down