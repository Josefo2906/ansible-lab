# Laboratorio de Docker y Ansible

## Objetivo de la práctica
Crear un entorno de laboratorio con dos servidores Linux (`server1` y `server2`) ejecutándose en contenedores Docker con Ubuntu 24.04 y administrarlos de forma automatizada mediante Ansible.

## Comandos para iniciar los contenedores

1. Levantar los servidores en segundo plano:

    docker compose up -d

2. Verificar que los contenedores estén activos:

    docker ps

3. Instalar Python 3 en cada contenedor:

    docker exec -it server1 bash -c "apt update && apt install -y python3"
    docker exec -it server2 bash -c "apt update && apt install -y python3"

## Comando para ejecutar el playbook

1. Verificar la conexión con los contenedores:

    ansible docker -i inventory.ini -m ping

2. Ejecutar el playbook:

    ansible-playbook -i inventory.ini playbook.yml

## Captura de pantalla de la ejecución exitosa

![Ejecución exitosa del playbook](./captura.png)
