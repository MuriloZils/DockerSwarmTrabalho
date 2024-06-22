# Tutorial Aplicação
## Docker Swarm, MySql, WordPress & Prometheus, Redis

1. Preparo para a excução
    1. Tenha o docker, git e WLS(Caso esteja no windows) instalados
    2. Verifique se as portas não estão sendo utilizadas

2. Criar o diretório
    1. Mkdir *Pasta*, cd *Pasta*
    2. git clone https://github.com/MuriloZils/DockerSwarmTrabalho
    3. cd DockerSwarmTrabalho

3. Rode os seguintes comandos
    * docker stack deploy -c docker.yml wordpress_stack
    * docker node ls
    * docker swarm init
    * docker node inspect -f '{{ .Status.Addr }} *Nome do Host*
    * docker ps
    * docker exec -it *id do container wordpress* bash
    * apt update
    * apt install nano
    * nano wp-config.php

    1. Adicione os seguintes comando entre as linhas
    ' if ($configExtra = getenv_docker('WORDPRESS_CONFIG_EXTRA', '')) {
        eval($configExtra);
        }

    /* That's all, stop editing! Happy publishing. */ '

    * define('WP_CACHE', true);
    * define('WP_REDIS_HOST', 'redis');
    * define('WP_REDIS_PORT', 6379);

    2. Utilize CTRL+X, Y e ENTER

4. Agora entre em http:// *ip da máquina lider*:80/admin
   
      1. Agora entre em http:// *ip da máquina lider*:80/admin
    * Vá em "Tools", e então em "Info", e procure "Database"
    
    * Agora vá em "plugins" "Add New Plugin", procure o "Redis", instale e ative
        * Então vá em "Configurações" e "Redis", então inicie o Redis

5. Agora entre em http:// *ip da máquina lider*:9090
    
    * A pagina deve aparecer a tela do Prometheus


# Fim.

## Murilo Zils
