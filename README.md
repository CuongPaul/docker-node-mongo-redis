1. Build image
   docker build -t learning-docker/docker-node-mongo-redis:v1 .

2. Truy cập vào container
   docker-compose exec <container_name> sh

3. Tạo một container tạm thời từ image node:13-alpine, chạy npm install và mount trực tiếp file ra môi trường ngoài, kết qủa là khi command kia chạy xong thì môi trường ngoài của ta sẽ có node_modules.
   docker run --rm -v $(pwd):/app -w /app node:13-alpine npm install

   # Note trên windows thì command trên chạy như sau:

   docker run --rm -v "/$(pwd)":/app -w //app node:13-alpine npm install
