Project Overview

Description:

This project is to enable rerouting of HTTP requests to my applications hosted in docker.
This eliminates the need to memorise multiple ip addresses and their respective ports.

Goals / Objectives

	• Configure and Deploy DNS server within docker.
	• Re-configure DNS server address on network devices
	• Configure DNS rewrite rules to forward http requests to docker host IP
	• Configure and Deploy NGINX for reverse proxy capabilities
	• Configure Proxy
	•  host to redirect source requests to applications listening on specific ports of the docker host

high level overview
<img width="1024" height="1536" alt="Network Traffic Flow Diagram" src="https://github.com/user-attachments/assets/85ff35db-73a0-4ddb-94fc-4949ec583f26" />


Configuring NGINX
Nginx docker-compose YAML file

Ensure Nginx is listening on the correct ports for HTTP and HTTPS traffic

Map docker port 80 - > Host port 80

Map docker port 443 - > Host port 443

Ensure NPM is listening on port 81 for the admin web portal

Map docker port 81 -> host port 81

<img width="635" height="544" alt="Adguard YAML" src="https://github.com/user-attachments/assets/5346d868-f8bd-4ceb-b894-8b75a46299a4" />

Restart the Nginx container to read the new configuration

<img width="2390" height="409" alt="Nginx container restart" src="https://github.com/user-attachments/assets/110d661f-2dcb-414e-9b72-c5e771b0d265" />

Configure Proxy hosts to forward Traffic from x-domain to x-ip/port

Checkmk admin portal is listening on port 8080

Java dashboard app is listening on port 8085

<img width="1197" height="394" alt="Rewrites" src="https://github.com/user-attachments/assets/c7d3a530-2b6b-4ded-8631-46559497f20b" />


	


