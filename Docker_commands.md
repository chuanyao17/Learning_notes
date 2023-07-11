docker run：運行一個容器。
範例：docker run <image_name>

docker ps：列出正在運行的容器。
範例：docker ps

docker images：列出本地的映像檔。
範例：docker images

docker stop：停止運行中的容器。
範例：docker stop <container_id>

docker start：啟動已停止的容器。
範例：docker start <container_id>

docker restart：重新啟動容器。
範例：docker restart <container_id>

docker rm：刪除容器。
範例：docker rm <container_id>

docker rmi：刪除映像檔。
範例：docker rmi <image_id>

docker exec：在運行中的容器中執行命令。
範例：docker exec <container_id> <command>

docker pull：下載映像檔。
範例：docker pull <image_name>

docker build：使用 Dockerfile 構建映像檔。
範例：docker build -t <image_name> <path_to_dockerfile>