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

- Thao tác trên các máy worker
- cài đặt docker-compose \
sudo apt install docker-compose -y
- chạy yml ngầm \
sudo docker-compose -f node_exporter.yml up -d

-# Dừng và xóa tất cả các container được tạo bởi docker-compose up\
sudo docker-compose -f docker-compose.yml down

= # Xóa tất cả các image không sử dụng để giải phóng dung lượng\
sudo docker image prune -a

