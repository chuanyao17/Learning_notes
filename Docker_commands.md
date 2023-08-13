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
docker exec -it [容器ID或名稱] /bin/bash，是為了在容器中進行故障排查、檢視文件、手動安裝軟體或進行其他需要直接與容器互動的操作。  
bash: "Bourne Again SHell" 的縮寫。它是原始 Bourne Shell (sh) 的替代品和擴展。bash 提供了許多改進和功能，如命令行編輯、命令歷史和命令補全等。大多數現代的 Linux 發行版默認都使用 bash 作為其主要 shell。  
當在 Docker 容器中運行 /bin/bash 時，您基本上是在該容器的上下文中啟動了一個新的 bash session。這意味著您現在可以在容器內部以互動的方式運行命令，就好像您直接在主機上操作一樣。  

docker pull：下載映像檔。
範例：docker pull <image_name>

docker build：使用 Dockerfile 構建映像檔。
範例：docker build -t <image_name> <path_to_dockerfile>