- Tạo 2 network \
coinswarmnet \
sudo docker network create --scope=swarm --attachable -d overlay --opt encrypted coinswarmnet \
loggingnet \
sudo docker network create --scope=swarm --attachable -d overlay loggingnet \
monitornet \
sudo docker network create --scope=swarm --attachable -d overlay monitornet

- Chạy docker stack \
sudo docker stack deploy -c elk.yml elk \
sudo docker stack deploy -c mrnam.yml mrnam 

- lệnh khởi động lại dịch vụ \
sudo docker service update --force elk_elasticsearch 

- lệnh xóa toàn bộ \
sudo docker system prune -a --volumes

- chạy yml ngầm \
sudo docker-compose -f node_exporter.yml up -d
