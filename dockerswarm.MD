Dockerswarm

docker run -it --rm docker/dtr install   --ucp-node bipratech2c.mylabserver.com   --ucp-username admin   --ucp-url https://172.31.17.178 --ucp-insecure-tls
change ucp controller port

docker service update --env-add CONTROLLER_PORT=port_num ucp-agent

