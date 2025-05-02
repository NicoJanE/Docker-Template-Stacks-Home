---
layout: default_c
RefPages:
 
--- 


# 1. what 

Generic description of **pluggable stack** Such a stacks is designed for easy integration with other stacks. Each stack handles a specific service, such as a database service for example.

## 2. How 

Each Docker Compose file contains a network definition like this:

```
networks:
  php_network2:							# Define a network, Changes this in case of external: true
    external: false					# See 1) explanation below
    name: php_network2
    driver: bridge 
    ipam:
      config:
        - subnet: ${FIXED_SUBNET}
		
services:
  mariadb:
    image: mariadb:10.7.8
    restart: "no"
    networks:    
        php_network2:                       # Use this Network
            ipv4_address: ${FIXED_IP}       # Use a fixed IP address for this container service
    environment:
      MARIADB_ROOT_PASSWORD: root
      MARIADB_DATABASE: docker
      MARIADB_USER: docker
      MARIADB_PASSWORD: docker
    ports:
      - "9004:3306"
    volumes:
      - mariadb:/var/lib/mysql
     
```
Setting the `external: true` defines an external network, allowing multiple Docker stack files to work together.
This works in combination with a **.env** file, which should contain:
- FIXED_IP
- IXED_SUBNET
> Note:  If `external: false`(default) Docker Compose automatically creates an internal network using the IP defined in .env. 
Such a service can not reach a service that is not defined in the same file!

### Instructions

To connect services to the same network, each service must use the **networks** setting and a unique **FIXED_IP**.
Make the following changes in all Docker Compose files:

- Set `external: true` in the network definition.
- Use the **same network name** (e.g., php_network) across **all** Docker Compose files.
- Make sure the same network Subnets is used (defined in .env file, make sure all services us this file)
- Ensure the **same subnet** is used (defined in the `.env` file).
- **Manually create the network before starting any services** (make sure to use the correct subnet).
	- **Example:** ``docker network create --subnet=${FIXED_SUBNET} php_network``
	- **Example delete :** ``docker network rm php_network``
  - **Other example :** ``docker network ls     # Displays networks``
  - **Other example :** ``docker network prune  # CAREFUL removes all unused!!``
<br>
	

#### Optional tests
- Optional Test, if both are on the same network: ``docker network inspect php_network``
-  Optional Test, if the cor rect IP address inside the container is used, enter: ``hostname -I``



<br><br>
<small> <i>version 1.0</i> </small>