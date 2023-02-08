# docker pull
```
sudo docker pull nvcr.io/nvidia/pytorch:22.12-py3

```



# docker create

```
xhost local:root

sudo docker run -itd  \
--name tidy-openvino_notebooks-2022.2 \
--user root \
--privileged \
-p 9802:6000 \
-v /etc/localtime:/etc/localtime \
--ipc=host \
-v /tmp/.X11-unix:/tmp/.X11-unix \
-e DISPLAY=$DISPLAY \
-v /data/home/baseuser/tidy-workspace/tidy-openvino_notebooks/openvino_notebooks-2022.2:/root/openvino_notebooks \
-w /root/openvino_notebooks nvcr.io/nvidia/pytorch:22.12-py3


```


# enter docker
```
xhost local:root
sudo docker stop tidy-openvino_notebooks-2022.2
sudo docker start tidy-openvino_notebooks-2022.2
sudo docker exec -it tidy-openvino_notebooks-2022.2 /bin/bash

```

# install
```
cd /root/openvino_notebooks/sources/openvino_notebooks
pip3 install -r requirements.txt

cd /root/openvino_notebooks
nohup jupyter notebook --ip=0.0.0.0 --allow-root --port 6000 &

http://localhost:9802/tree

```



