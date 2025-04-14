- Tạo 2 network \
coinswarmnet \
sudo docker network create --scope=swarm --attachable -d overlay --opt encrypted coinswarmnet \
loggingnet \
sudo docker network create --scope=swarm --attachable -d overlay loggingnet \

- Chạy docker stack \
sudo docker stack deploy -c elk.yml elk \
sudo docker stack deploy -c mrnam.yml mrnam \

- lệnh khởi động lại dịch vụ \
sudo docker service update --force elk_elasticsearch \

- lệnh xóa toàn bộ \
sudo docker system prune -a --volumes \
